# Disable subtitles and jumping icons in Nextcloud 15

I used [Custom CSS](https://apps.nextcloud.com/apps/theming_customcss) and [JSLoader](https://apps.nextcloud.com/apps/jsloader) to adapt the app menu to my preferences.

``` css
/* Disable subtitles and jumping icons */
#appmenu li span {
  display: none;
}

#appmenu li:hover a + span,
#appmenu li a:focus + span, #appmenu li:hover span, #appmenu li:focus span,
#appmenu li a:focus span {
  display: none;
}

#appmenu:hover li svg,
#appmenu:hover li .icon-more,
#appmenu:hover li .icon-more-white,
#appmenu:hover li .icon-loading-small,
#appmenu:hover li .icon-loading-small-dark {
  transform: none;
}

#appmenu li a:focus svg,
#appmenu li a:focus .icon-more,
#appmenu li a:focus .icon-more-white,
#appmenu li a:focus .icon-loading-small,
#appmenu li a:focus .icon-loading-small-dark {
  transform: none;
}

/* Disable triangle below icons */
#appmenu li a.active::before, #appmenu li:hover a::before, #appmenu li:hover a.active::before, #appmenu li a:focus::before {
  display: none;
}

```

``` javascript
// Add title tags to the app menu entries
var children = document.getElementById("appmenu").children;
  for (var i = 0; i < children.length; i++)  
  {
    document.getElementById("appmenu").children[i].title=document.getElementById("appmenu").children[i].textContent;
  }
```