## Live at [IPL Visualizer](https://neildahiya.github.io/IPL_VISUALIZER)

#### Data analysis [Repo](https://github.com/neildahiya/ipl_analysed_data)

![Imgur](https://i.imgur.com/TrLYlZZ.png)

# Libraries/Frameworks Used

- vue-ui
- vue-router
- vue/pwa
- [charts.js](<[https://www.chartjs.org/](https://www.chartjs.org/)>)
- Bootstrap (for styling)

# Bonus Tasks

### Created in VueJS :white_check_mark:

- Hadn't worked in Vue before, so had to do a crash course on Youtube.

### Optimized Loading Time :white_check_mark:

- Analysed the data from the datasets in Python first using pandas, numpy, matplotlib, etc. so that entire CSV file doesn't need to be loaded and we get clean and concise data.
- Vue automatically minifies the CSS and JS files.
- Did **Lighthouse** testing and improved on various alarms raised.

### Mobile Responsive :white_check_mark:

- Done using Bootstrap responsive components and media queries
- **Lighthouse** reports can be found below.

### Progressive web-app :part_alternation_mark:

- Couldn't successfully do the caching after registering the service worker.
- It gets registered and caching was working, but I wasn't able to use that cache properly.
- So removed the registerServiceWorker file (can be seen in previous commits).

### Offline Functionality :heavy_exclamation_mark:

- Couldn't do this as converting to PWA didn't work (still trying to debug).

## Lighthouse Audit

![Imgur](https://i.imgur.com/RJXziLc.jpg)

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

### Compiles and minifies for production

```
yarn build
```

### Lints and fixes files

```
yarn lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
