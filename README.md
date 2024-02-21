This Bookmarklet can be added to your browser to export a linkedin post into a json file:

To add a bookmark in Google Chrome that runs a JavaScript function, you'll be creating what's often referred to as a "bookmarklet." 
These are handy for automating frequent tasks or enhancing your browsing experience. 
Here's how to do it:

Open Chrome: Launch your Google Chrome browser.
Show the Bookmarks Bar: If your bookmarks bar isn't already visible, you can show it by pressing Ctrl+Shift+B on Windows or Command+Shift+B on macOS. Alternatively, you can click on the three vertical dots in the top right corner of the browser, go to "Bookmarks," and then select "Show bookmarks bar."

Add a Bookmark: You can add a bookmark in a few ways, but here's an easy one:

Right-click on the bookmarks bar.
Choose "Add page..." from the context menu.
Edit the Bookmark Details:

In the "Name" field, enter a descriptive name for your bookmarklet. This is what will appear on your bookmarks bar.
In the "URL" field, paste the LinkedInPost Export script. 
  
Ensure it starts with javascript: (this is crucial for the browser to recognize it as a script). For example, your script should look something like this:
javascript:(function()%7Bfunction scrapeData()%7Bconst result%3D%7B%7D%3Bconst backgroundImageDiv%3Ddocument.querySelector('.profile-rail-card__member-bg-image')%3Bif(backgroundImageDiv)%7Bconst backgroundImageStyle%3DbackgroundImageDiv.style.backgroundImage%3Bconst urlMatch%3D%2Furl%5C("(.%2B%3F)"%5C)%2F.exec(backgroundImageStyle)%3Bif(urlMatch)%7Bresult.backgroundImageUrl%3DurlMatch%5B1%5D%3B%7D%7Dconst profileImage%3Ddocument.querySelector('.profile-rail-card__member-photo')%3Bif(profileImage)%7Bresult.profileImageUrl%3DprofileImage.src%3B%7Dconst profileName%3Ddocument.querySelector('.profile-rail-card__name span%5Baria-hidden%3D"true"%5D')%3Bif(profileName)%7Bresult.profileName%3DprofileName.textContent%3B%7Dconst profileDescription%3Ddocument.querySelector('.profile-rail-card__description span%5Baria-hidden%3D"true"%5D')%3Bif(profileDescription)%7Bresult.profileDescription%3DprofileDescription.textContent%3B%7Dconst postDiv%3Ddocument.querySelector('.update-components-text.relative.update-components-update-v2__commentary')%3Bif(postDiv)%7Bresult.linkedInPostText%3DpostDiv.textContent.trim()%7C%7CpostDiv.innerText.trim()%3B%7Dreturn result%3B%7Dfunction downloadJson(data%2Cfilename)%7Bconst jsonStr%3DJSON.stringify(data%2Cnull%2C2)%3Bconst blob%3Dnew Blob(%5BjsonStr%5D%2C%7Btype%3A"application%2Fjson"%7D)%3Bconst url%3DURL.createObjectURL(blob)%3Bconst a%3Ddocument.createElement("a")%3Ba.href%3Durl%3Ba.download%3Dfilename%3Ba.textContent%3D"Download JSON"%3Bdocument.body.appendChild(a)%3Ba.click()%3Bdocument.body.removeChild(a)%3BURL.revokeObjectURL(url)%3B%7Dconst scrapedData%3DscrapeData()%3BdownloadJson(scrapedData%2C"exportedData.json")%3B%7D)()

Save the Bookmarklet: Click "Save." The bookmarklet will now appear on your bookmarks bar.

Using Your Bookmarklet: Whenever you want to run the script, simply click on its name on your bookmarks bar. The JavaScript will execute on the current page you're viewing.
