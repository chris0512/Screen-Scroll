# Screen-Scroll

This side project load the images from Unsplash api [random-photo-api](https://unsplash.com/documentation#get-a-random-photo)

![api-png](unsplash-api.png)

Fetch the image by API:
```js
const apiUrl = `https://api.unsplash.com/photos/random/?client_id=${apiKey}&count=${count}`;

async function getPhotos() {
    try {
        const response = await fetch(apiUrl);
        photosArray = await response.json();
        console.log(photosArray);
    } catch (error) {

    }
}
```
<br/>

When scrolling near the bottom of page and image is loaded, load more photos:
```js

window.addEventListener('scroll', () => {
    if (window.innerHeight + window.scrollY >= document.body.offsetHeight - 1000 && ready) {
        ready = false;
        getPhotos();

    }
})
```
```js
function imageLoaded() {
    imagesLoaded++;
    console.log(imagesLoaded);
    if (imagesLoaded === totalImages) {
        ready = true;
        loader.hidden = true;
        console.log('ready = ', ready);
    }
}
```
<br/>
