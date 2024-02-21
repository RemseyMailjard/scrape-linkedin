LinkedIn Post Export Bookmarklet

This Bookmarklet can be added to your browser to export a LinkedIn post into a JSON file. Follow the steps below to add the Bookmarklet to Google Chrome:

# How to Install LinkedIn Bookmarklet

Follow the instructions below to add the LinkedIn Post Export Bookmarklet to your browser. For a visual guide, see the video tutorial.

## Video Tutorial

[![How to Install LinkedIn Bookmarklet]([https://img.youtube.com/vi/VIDEO_ID/0.jpg)](https://youtu.be/-DRPBM_p0v4)](./how-to-install-linkedin-bookmarklet.mp4 "How to Install LinkedIn Bookmarklet - Click to Watch!")


## Installation Instructions


1. **Open Chrome**: Launch your Google Chrome browser.

2. **Show the Bookmarks Bar**:
    - If your bookmarks bar isn't already visible, you can enable it by pressing `Ctrl+Shift+B` on Windows or `Command+Shift+B` on macOS.
    - Alternatively, click on the three vertical dots in the top right corner of the browser, go to "Bookmarks," and then select "Show bookmarks bar."

3. **Add a Bookmark**:
    - Right-click on the bookmarks bar.
    - Choose "Add page..." from the context menu.

4. **Edit the Bookmark Details**:
    - In the "Name" field, enter a descriptive name for your bookmarklet, such as "LinkedIn Post Export."
    - In the "URL" field, paste the following LinkedIn Post Export script:

        ```javascript
        javascript:(function()%7Bfunction scrapeData()%7Bconst result%3D%7B%7D%3Bconst backgroundImageDiv%3Ddocument.querySelector('.profile-rail-card__member-bg-image')%3Bif(backgroundImageDiv)%7Bconst backgroundImageStyle%3DbackgroundImageDiv.style.backgroundImage%3Bconst urlMatch%3D%2Furl%5C("(.%2B%3F)"%5C)%2F.exec(backgroundImageStyle)%3Bif(urlMatch)%7Bresult.backgroundImageUrl%3DurlMatch%5B1%5D%3B%7D%7Dconst profileImage%3Ddocument.querySelector('.profile-rail-card__member-photo')%3Bif(profileImage)%7Bresult.profileImageUrl%3DprofileImage.src%3B%7Dconst profileName%3Ddocument.querySelector('.profile-rail-card__name span%5Baria-hidden%3D"true"%5D')%3Bif(profileName)%7Bresult.profileName%3DprofileName.textContent%3B%7Dconst profileDescription%3Ddocument.querySelector('.profile-rail-card__description span%5Baria-hidden%3D"true"%5D')%3Bif(profileDescription)%7Bresult.profileDescription%3DprofileDescription.textContent%3B%7Dconst postDiv%3Ddocument.querySelector('.update-components-text.relative.update-components-update-v2__commentary')%3Bif(postDiv)%7Bresult.linkedInPostText%3DpostDiv.textContent.trim()%7C%7CpostDiv.innerText.trim()%3B%7Dreturn result%3B%7Dfunction downloadJson(data%2Cfilename)%7Bconst jsonStr%3DJSON.stringify(data%2Cnull%2C2)%3Bconst blob%3Dnew Blob(%5BjsonStr%5D%2C%7Btype%3A"application%2Fjson"%7D)%3Bconst url%3DURL.createObjectURL(blob)%3Bconst a%3Ddocument.createElement("a")%3Ba.href%3Durl%3Ba.download%3Dfilename%3Ba.textContent%3D"Download JSON"%3Bdocument.body.appendChild(a)%3Ba.click()%3Bdocument.body.removeChild(a)%3BURL.revokeObjectURL(url)%3B%7Dconst scrapedData%3DscrapeData()%3BdownloadJson(scrapedData%2C"exportedData.json")%3B%7D)()
        ```

    - Ensure it starts with `javascript:` (this is crucial for the browser to recognize it as a script).

5. **Save the Bookmarklet**:
    - Click "Save." The bookmarklet will now appear on your bookmarks bar.

## Usage

- Whenever you want to run the script, simply click on its name on your bookmarks bar. The JavaScript will execute on the current page you're viewing, and a JSON file with the exported data will be downloaded to your computer.

## Security Note

- Be cautious when using bookmarklets from untrusted sources, as they can execute arbitrary code on your behalf.

Ensure it starts with javascript: (this is crucial for the browser to recognize it as a script). For example, your script should look something like this:

