# Dropbox-video-embed-Jekyll
How to embed Dropbox video on Jekyll

open folder `_includes` then create file `dropboxplayer.html` with this code:

```
<div class="embed-container">
  <iframe
      width="640"
      height="480"
      src="https://www.dropbox.com/s/{{ include.id }}?raw=1"
      frameborder="0"
      allowfullscreen="">
  </iframe>
</div>
```

add CSS create file `video-embed.scss` in `_sass` with this code:

```
.embed-container {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  max-width: 100%;
}

.embed-container iframe, .embed-container object, .embed-container embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```
open file `styles.scss` and put this code `@import "video-embed.scss`

then put this code wherever you want in your .md file

```
{% include dropboxplayer.html id=page.dropboxvid %}
```
add your Dropbox video id here on top of your .md file:

```
layout: post
title: Your Title Here
dropboxvid: your dropbox video ID
```

find your dropbox link, it will be like this:
```
https://www.dropbox.com/s/p4b33wnl8y4752m/MNJMNC14.mp4?dl=0
```

so it will be like this:

```
layout: post
title: Your Title Here
dropboxvid: p4b33wnl8y4752m/MNJMNC14.mp4
```

boom, your dropbox video is ready ! but you have to know that dropbox has a limitation on video bandwith. it depands on size of your video.

***Reference:***

[https://github.com/nathancy/jekyll-embed-video](https://github.com/nathancy/jekyll-embed-video)
