# Screen-Scroll

This side project load the images from Unsplash api [random-photo-api](https://unsplash.com/documentation#get-a-random-photo)



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
