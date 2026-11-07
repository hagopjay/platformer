# platformer

Hosts playable builds of KANSEI, a night-drift racing game whose worlds are X3D files, drawn by Babylon.js (WebGPU).

- Site: https://hagopjay.github.io/platformer/
- `kansei/v1.1/` is the current build: the same game and picture as v1, with the texture-fallback fix (about 2,350 failed requests on the live page before).
- `kansei/v1/` is the first Babylon WebGPU build. Each version gets its own folder and is never overwritten.
- `index.html` is the landing page.

The game and the Babylon port are developed in [hagopjay/x3d.loom](https://github.com/hagopjay/x3d.loom) (`x3d.drift`, `x3d.webgpu/demo`). A build is made with:

```sh
python3 -I x3d.webgpu/demo/src/build-drift.py --game x3d.drift --out kansei/vN
```

Babylon.js 9.32.0 loads from a CDN with a subresource-integrity hash. The page needs a WebGPU browser; on some Windows machines Chrome needs `chrome://flags/#enable-unsafe-webgpu` set to Enabled.
