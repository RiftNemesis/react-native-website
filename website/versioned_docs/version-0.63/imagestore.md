---
id: imagestore
title: ImageStore
---

> **Deprecated.** Use one of the [community packages](https://reactnative.directory/?search=file) instead.

### Methods

- [`hasImageForTag`](imagestore.md#hasimagefortag)
- [`removeImageForTag`](imagestore.md#removeimagefortag)
- [`addImageFromBase64`](imagestore.md#addimagefrombase64)
- [`getBase64ForTag`](imagestore.md#getbase64fortag)

---

# Reference

## Methods

### `hasImageForTag()`

```jsx
static hasImageForTag(uri, callback)
```

Check if the ImageStore contains image data for the specified URI. @platform ios

---

### `removeImageForTag()`

```jsx
static removeImageForTag(uri)
```

Delete an image from the ImageStore. Images are stored in memory and must be manually removed when you are finished with them, otherwise they will continue to use up RAM until the app is terminated. It is safe to call `removeImageForTag()` without first calling `hasImageForTag()`, it will fail silently. @platform ios

---

### `addImageFromBase64()`

```jsx
static addImageFromBase64(base64ImageData, success, failure)
```

Stores a base64-encoded image in the ImageStore, and returns a URI that can be used to access or display the image later. Images are stored in memory only, and must be manually deleted when you are finished with them by calling `removeImageForTag()`.

Note that it is very inefficient to transfer large quantities of binary data between JS and native code, so you should avoid calling this more than necessary. @platform ios

---

### `getBase64ForTag()`

```jsx
static getBase64ForTag(uri, success, failure)
```

Retrieves the base64-encoded data for an image in the ImageStore. If the specified URI does not match an image in the store, the failure callback will be called.

Note that it is very inefficient to transfer large quantities of binary data between JS and native code, so you should avoid calling this more than necessary. To display an image in the ImageStore, you can pass the URI to an `<Image/>` component; there is no need to retrieve the base64 data.