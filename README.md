# skillshare_downloader

A bash script to download Skillshare classes with a premium account. It gets class information, passes the stream information to `yt-dlp` and downloads it.

## Usage
```
Usage: skillshare_downloader [-rx] (-c class_id) [-j /path/to/headers] [-d /path/to/output] [-y "<extra yt-dlp options>"]

Options:
    -c:     [Required] Class id; taken from the url 
            (https://www.skillshare.com/en/classes/full-class-name/<class id>)

    -j:     Path to request headers; found by inspecting the network
            request made to Skillshare (default: $HOME/.config/skillshare.headers)

    -d:     Path to output directory of video files (default: $PWD)

    -r:     Refresh class details; useful if class has been updated
            (will use cache by default)

    -y:     Pass extra options to yt-dlp

    -h:     Show this help message

    -x:     Enable debug logging
```

To acquire the request headers, follow these steps:
1. Go to [https://skillshare.com](skillshare.com) and select a class
2. Open the Developer tools in Chromium-based or Firefox-based browsers:
   * Windows/Linux: Use the shortcut `F12`
    * MacOS: Use the shortcut `Cmd + Alt + I`
3. Switch to the Network tab
4. Refresh the page
5. Scroll to the top of the request list
6. Right-click on the top request (the request for the class page) and select:
   * Firefox: "Copy Value > Copy request headers"
    * Chrome: "Copy > Copy as cURL"
7. Paste this into a file such as `~/.config/skillshare.headers`

## Dependencies
* [yt-dlp](https://github.com/yt-dlp/yt-dlp)
* [jq](https://github.com/jqlang/jq)

## License
GNU General Public License v3.0
