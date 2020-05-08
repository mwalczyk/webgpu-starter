# Installation

Install webpack dependencies (and webpack support for TypeScript):
1. `webpack`
2. `webpack-cli`
3. `typescript`
4. `ts-loader`

Create the webpack configuration file: `webpack.config.js`. Add the `watch: true` flag so that we can use live reloading. You can run webpack with `webpack --config webpack.config.js`.

Create the TypeScript configuration file: `tsconfig.json`. Make sure this is targeting ES5 (why?). 

Install `@webgpu/types` (type definitions for all WebGPU objects). Make sure a reference to this script exists in your main scripts: `<reference path="../node_modules/@webgpu/types/dist/index.d.ts"/>`.

Install `http-server` (for loading SPIR-V modules with CORS). 

If you need to edit any of the GLSL shaders, you must install `glslangValidator` and run:

```
glslangValidator -V triangle.vert -o triangle.vert.spv
glslangValidator -V triangle.frag -o triangle.frag.spv
```

## Issues

For some reason, in Chrome Canary, you have to right-click the reload button and select "Hard Reload" when refreshing the page or updating scripts. Apparently, this is a caching issue. This could be something basic that I'm doing wrong because I'm not a web developer!

## References

[Alain Galvan's Tutorial](https://alain.xyz/blog/raw-webgpu)