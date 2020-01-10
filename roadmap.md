# Libé Labo : roadmap

| Done | Repo                     | Component               | Task                                                                      | Comment                                            |
| ---- | ------------------------ | ----------------------- | ------------------------------------------------------------------------- | -------------------------------------------------- |
|  ✅  | `libe-apps-template`     | `package.json`          | Write a build script (with SEO tags written in public/index.hml)          |                                                    |
|  ✅  | `libe-components`        | `ArticleMeta`           | input dates to format YYYY/MM/DD HH:MM                                    |                                                    |
|  ❌  | `libe-components`        | `Hero`                  | Text and illustration should be positionned via the Grid/Slot objects     | Not sure if a good idea                            |
|  ✅  | `paris-populaire`        | `Filters`               | Figure out why some points are present in wrong time periods              | Not found                                          |
|  ✅  | `paris-populaire`        | `Tooltips`              | Figure out why dates don't display consistently the same data             | Displays only years by default, only one if start & end in same year|
|  ✅  | `libe-apps-template`     | `App.js`                | Place a default ShareArticle component                                    |                                                    |
|  ✅  | `libe-apps-template`     | `App.js`                | Place a default LibeLaboLogo component                                    |                                                    |
|      | `libe-data-server`       | `database`              | Build a cron db backup                                                    |                                                    |
|  ✅  | `libe-data-server`       | `database`              | Renew subscription                                                        |                                                    |
|      | `libe-components`        | `ArticleMeta`           | Error if no authors are given                                             |                                                    |
|      | `libe-components`        | `Grid & Slot`           | Should be working even if no params or empty                              |                                                    |
|      | `libe-apps-template`     | `build.js`              | Load spreadsheet, get SEO elements and save a data preload                |                                                    |
|      | `libe-apps-template`     | `index.js`              | Fix broken static link when loading dev version over local ip             |                                                    |
|      | `libe-components`        | `Photo`                 | Hide empty descriptions or credits                                        |                                                    |
|      | `libe-components`        | `NEW`                   | Video embed, audio embed, iframe, playlist, diaporama, ...                |                                                    |
|      | `libe-components`        | `JSXInterpreter`        | Should work with empty attributes eg: \<audio controls>                   |                                                    |
|      | `libe-apps-template`     | `build.js`              | Add an option to remove sourcemaps from build                             |                                                    |
|      | `libe-components`        | `Icon`                  | Display a \<Svg> of an icon in static-ressources, with only name and size props|                                               |
|      | `libe-apps-template`     | `config.js`             | Implement dev and prod spreadsheets logic                                 |                                                    |
|      | `libe-components`        | –                       | Make a good looking front-page, host it in libe-static-ressources, and update libe-component's README.|                        |
|      | `libe-static-ressources` | –                       | "Ressources" is not correct in english, it's "resources"                  |                                                    |
|      | `libe-static-ressources` | `components.css/lblb-video`| Fix css here                                                           |                                                    |
|      | `libe-utils`             | `parseTsv`              | Should work without the second parameter                                  |                                                    |
|      | `libe-apps-template`     | `config.js`             | /src/config.js is imported the ES6 way in /src/App.js and required in /build.js|                                               |
|      | `libe-data-server`       | -                       | Finish total re-write                                                          |                                               |
