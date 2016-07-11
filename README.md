# JW Showcase

JW Showcase is an open-source, dynamically generated video website built around [JW Player](http://www.jwplayer.com) and JW Platform services. It enables you to easily publish your JW Player-hosted video content with no coding and minimal configuration.

You can use JW Showcase with other content delivery platforms (or your own CDN), but you will need to modify the source code.

## Supported Features

- Works with any JW Player edition, from Free to Enterprise (note that usage will count against your monthly JW streaming limits). Only cloud-hosted JW Players are supported.
- Populates your site's media content using JSON feeds. If you are using JW Platform, this happens auto-magically based on playlists that you specify. Using feeds from other sources will require you to hack the source code.
- Video titles, descriptions and hero images are populated from JW Platform JSON feed metadata.
- Playback of HLS video content from the JW Platform CDN. You can add external URLs (for example, URLS from your own server or CDN) to your playlists in the Content section of your JW Player account dashboard, but they must be HLS streams (`.m3u8` files).
- Customize the user interface with your own branding. The default app is configured for JW Player branding and content but you can easily change this to use your own assets by modifying the `config.json`. Advanced customization is possible (for example, editing the CSS files) , but you will need to modify the source code.
- Basic playback analytics reporting to your JW Dashboard.
- Ad integrations (VAST, VPAID, GoogleIMA, etc.)

### Unsupported Features

- Security-related features (encrypted HLS, DRM, signed URLs)
- Search
- Self-hosted JW Players

## Instructions for Using JW Showcase

For full instructions, see the JW Showcase [Wiki pages](https://github.com/jwplayer/jw-showcase/wiki/):

* [Getting Started](https://github.com/jwplayer/jw-showcase/wiki/Getting-Started)
* [Deploying JW Showcase](https://github.com/jwplayer/jw-showcase/wiki/Deploying-jw-showcase)
* [Search Engines and Social Sharing](https://github.com/jwplayer/jw-showcase/wiki/Search-engines-and-social-sharing)

### Basic Setup

1. Download the latest [pre-compiled stable release](https://github.com/jwplayer/jw-showcase/releases).
2. Extract the release archive to your web server.
3. By default, JW Showcase assumes the site is in your top-level web document root (/). If you want to use a subdirectory (for example, /video/), edit the `index.html` file and replace the slash in &lt;base href="/"&gt; with your directory (for example, &lt;base href="/video/"&gt;).
3. Create a player in the [JW Player Dashboard](https://dashboard.jwplayer.com/#/players) and get its `player key`.
    - The player key is the eight-character identifier of the player, not your JW Player license key. 
    - To get the player key, in the JW Dashboard go to **Players** &gt; **Tools**. In the **Cloud Hosted Player Libraries** section at the top of the page, select the player you want to use from the **Player Title** drop down. Then, in the **Cloud Player Library URL** field, copy the eight-character value that appears just before `.js`. This value is the Player key. 
    - For example, if your Cloud Player Library URL is https://content.jwplatform.com/libraries/BHYYA1V3.js, your player key is **BHYYA1V3**.
4. Create one or more video playlist(s) in the [JW Player Dashboard](https://dashboard.jwplayer.com/#/content/playlists) and record their eight-character playlist IDs.
5. Configure your site by editing the `config.json` file in the directory where you extracted the JW Showcase release files.
    - Use the player key from the previously step in the `player` field.
    - Use playlist IDs for the `featuredPlaylist` and `playlists` key.
6. Visit your site.

## Support and Bug Reporting 

To report bugs and feature requests, or request help using JW Showcase, use this repository's [Issues](https://github.com/jwplayer/jw-showcase/issues) page.
