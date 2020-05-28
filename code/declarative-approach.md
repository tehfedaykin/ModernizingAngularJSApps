### Declartative (Reactive) Approach

```javascript
//one source of truth for galleries array
sortedGalleries$ = 
  // getting galleries from the API
  this.galleryService.getGalleries().pipe(
    // setting UI controlling props
    map((galleryRes) => galleryRes.data.map((gallery) => {...gallery, visible: true})),
    // event stream from user selection
    withLatestFrom(this.selectedSortBy$),
    switchMap(([mappedGalleryData, selectedSortBy]) => {
      switch(selectedSortBy) {
        //logic for sorting galleries
        return sortedGallery
      }
    })
  )
```