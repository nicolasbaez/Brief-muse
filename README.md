# Brief-muse
watching you through your memories

![buh](https://github.com/nicolasbaez/Brief-muse/blob/main/xp053.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
d = 24;
n = 0.01;
draw = (_) => {
  h = w / 2;
  for (i = -h; i < h; i += d)
    for (j = -h; j < h; j += d) {
      fill(abs(i), abs(j), h);
      quad(
        i,
        j,
        noise(i * n, j * n, k) * w,
        i + d,
        j,
        noise((i + d) * n, j * n, k) * w,
        i + d,
        j + d,
        noise((i + d) * n, (j + d) * n, k) * w,
        i,
        j + d,
        noise(i * n, (j + d) * n, k) * w
      );
    }
  if (k == 0) saveGif("xp053.gif", 500, { delay: 0, units: "frames" });
  k += n;
};
