### Imperative Approach

```javascript
let galleries = this.galleryService.getGalleries();

let selectedGalleries = []

setUpGalleryStuff() {
  this.galleries.map((gallery) => {
    return {
      ...gallery, 
      visbile: true
    }
  })
}

sortGalleriesByDate() {
  this.galleries.sort(function (a, b) {
    return a.createDate - b.createDate;
  });
}

addGallery(gallery) {
  this.galleries.push(gallery);
} 

selectGallery(gallery) {
  this.selectedGalleries.push(gallery);
}

deleteGallery(galleryId) {
  this.galleries.find((gallery) => gallery.id === galleryId);
  this.galleries.splice 
    ...
}

// and 600+ lines of more weird gallery manipulating code
```