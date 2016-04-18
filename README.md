# Project χ

Project χ (pronounced project /ˈ</span><span title="'k' in 'kind'">k</span><span title="/aɪ/ long 'i' in 'tide'">aɪ</span></span>/) is an modular open source visualization gallery toolkit.  It offers a framework and toolset for building self-hosted data-centric visualization websites. Geared towards sharing of supplemental materials associated with scientific publications; Project χ allows visitors to interact with visualizations, download associated data and images, and even try the visualization with their own uploaded or publicly available datasets.  For developers the framework comes preconfigured with the popular design frameworks (Twitter Bootstrap, Angular UI) and cutting edge build tools (gulp, jspm, SystemJS) and examples integrating interactive visualizations using [d3.js](http://d3js.org/), [AngularJS](https://angularjs.org/), and [BioJS](http://biojs.io/).

**Note: Project χ is experimental.  Many things will change.  If you are interested in this project or have issues please feel free to contact me.**

## Features

* Contains AngularJS services and directives for loading, parsing, and downloading tabular data and as well as downloading generated publication quality SVG images.
* Simple,  modular, and customizable design using [AngularJS](https://angularjs.org/) templates and [bootstrap](http://getbootstrap.com/) CSS framework.
* Supports CommonJS, AMD, and ES6 modules using the [SystemJS](https://github.com/systemjs/systemjs) universal dynamic module loader.
* Integrate additional visualizations, including [BioJS](http://biojs.io/) and [Chiasm](https://github.com/curran/chiasm) modules, directly from any registry such as [NPM](https://www.npmjs.com) or [GitHub](https://github.com/) using [JSPM](http://jspm.io/).
* Self-hosted fully client-side application doesn't require a server; easily hosted on [WebDAV](https://en.wikipedia.org/wiki/WebDAV) or [GitHub Pages](https://pages.github.com/).
* For production builds ES6 into ES5 including minification and bundling using [Gulp](http://gulpjs.com/) and [SystemJS Builder](https://github.com/systemjs/builder).

# For Developers

## Background

If you are not familiar it would be worthwhile to read up on [jspm](http://jspm.io/), [SystemJS](https://github.com/systemjs/systemjs), and [gulp](http://gulpjs.com/).

If you don't already have jspm or gulp you should install them globally.

```bash
npm install -g gulp-cli jspm
```

## Install

```bash
git clone https://github.com/Hypercubed/Project-Chi.git
cd Project-Chi
npm install # jspm install is run post-install by npm
```

## Run

```
gulp server
```

## Gulp Tasks

* `gulp server`, run development server
* `gulp build`, build distribution directory
* `gulp server:dist`, run distribution server for testing
* `gulp deploy`, push to gh-pages
* `gulp run`, run development server, karma tests and watch for file changes

## File Structure

```
/root
  +- package.json         # metadata used by NPM and JSPM
  +- gulpfile.js          # gulp build script
  +- karma.conf.js        # test configuration
  +- app/                 # application resources
    +- jspm_packages/     # jspm packages are installed here
    +- components/        # site components, including tests
    +- common/            # shared tools that are not components, including tests
    +- system.config.js   # SystemJS configuration generated by jspm
    +- index.html         # single page application
  +- dataset/             # datasets, see below
    +- example/           # default example dataset
  +- dist/                # build goes here
```

## Separation of template and dataset

By default all content in the `app` directory will be served by the development server when running `gulp server` and built into the `dist` folder when running `gulp build`.  However, to encourage contribution back to the `project-x` repository and enable using the same `project-x` source across multiple projects the developer may optionally put project specific data into a separate directory.  This folder can then be served and built along with the `project-x` core.  For example, if you create a `myProject` folder inside the `dataset` directory the following commands will work as indicated:

* `gulp server --dataset ./dataset/myProject`

	runs the development server serving the combination of the `app` directory and `dataset/myProject` directories as the web root.  Files in `dataset/myProject` override `app`.  If no dataset is given `./dataset/myProject` is assumed.

* `gulp build --dataset ./dataset/myProject`

  build distribution directory combining and bundling resources from the the `app` directory and `dataset/myProject` into the `dist` directory.  Files in `dataset/myProject` override `app`.

## Provided services and directives

TBR

## Contributing

Yes, [please](https://github.com/Hypercubed/Project-chi/issues).

# Acknowledgments

This work was supported by a research grant from the Japanese Ministry of Education, Culture, Sports, Science and Technology (MEXT) to the RIKEN Center for Life Science Technologies.

## Reference

TBR

## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)

Copyright (c) 2015-2016 RIKEN, Japan.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
