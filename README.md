# a11y-focus

## To Install
```
yarn install a11y-focus
```

### To Use For Navigation
```
<template>
    <a11y-focus route="true">
        <router-view></router-view>
    </a11y-focus>
</template>
```
### To Use For Asynchronous Data
```
<template>
    <a11y-focus route="data">
        <div>
            {{ message }}
        </div>
    </a11y-focus>
</template>
<script>
export default {
    data() {
        const self = this
        setTimeout (()=>{
            self.message = 'Data loading complete.'
        },2000)
        return {
            message: 'loading'
        }
    }
}
</script>
```


### Status

a11y-focus is in an alpha release state. 

To-do:
* Add unit tests

### Background
a11y-focus was created to make Single Page Applications (SPA) more accesible to those with low or impaired vision. Use the a11y-focus component wherever you want dynamic data to be immediately read upon loading. 

The acronym a11y (NOTE 11 is the number eleven, not two l's) standes for accessibility. Individuals with low or impaired vision often use screen readers to access information on websites. By default screen readers do not immediately speak updates pulled into the DOM dynamically (e.g. via routes or asynchronous API calls)

The a11y-focus component watches the vuex-router and/or child components and automatically causes the screen reader to begin reading whenever a route is changed or child component data is changed. You can use the data and route props to determine which events trigger the screen reader.

### Live Demo and More Information:

[PixelThin](http://www.pixelthin.com)
