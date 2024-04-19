# 𝕏 Show All

This is a bookmarklet for 𝕏 (Twitter) that will automatically click the "Show" button on sensitive content.

You were going to click it anyway. Let this bookmarklet do it for you!

## Setup

1. Create a new bookmark.
1. The bookmark name can be anything you want.
1. Copy paste this minified javascript and use it as the bookmark URL.
1. Save your new bookmark.

```javascript
javascript:(()=>{if(!["twitter.com","x.com"].includes(window.location.hostname))return;const t=["Show"],e=setInterval((()=>document.querySelectorAll('div[role="button"]').forEach((e=>{t.some((t=>t===e.textContent.trim()))&&e.click()}))),1e3);setTimeout((()=>clearInterval(e)),6e5)})();
```

## Usage

1. Click your new bookmark when you see content hidden behind the "Show" button.
1. Watch everything magically reveal itself!

The bookmarklet will continue working for 10 minutes before automatically stopping. It will also stop if you navigate away from 𝕏 or reload the site.

Simply click the bookmark again if needed.

## Troubleshooting

In Microsoft Edge, activating the bookmarklet from the favorites dropdown menu may not work. You will need to activate it from the favorites bar, which can be toggled with Ctrl+Shift+B.

## Code

This is the unminified javascript code. It should work on all major modern browsers.

```javascript
javascript:(() => {
  const targetHosts = ['twitter.com', 'x.com'];
  if (!targetHosts.includes(window.location.hostname)) {
    return;
  }
  const intervalDelay = 1000; // 1,000 ms = 1 sec
  const timeoutDelay = 600000; // 600,000 ms = 10 min
  const showText = ['Show'];
  const showAll = () => document.querySelectorAll('div[role="button"]').forEach(button => {
    if (showText.some(str => str === button.textContent.trim())) button.click();
  });
  const intervalId = setInterval(showAll, intervalDelay);
  setTimeout(() => clearInterval(intervalId), timeoutDelay);
})();
```

## Support

Please like and share this with anyone that might find it useful.

You can also follow me on 𝕏 @ [NeonNoodle22](https://x.com/NeonNoodle22).

I appreciate it!
