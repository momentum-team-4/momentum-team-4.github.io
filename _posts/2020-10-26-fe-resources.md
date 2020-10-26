---
layout: post
title: FE - File Upload and PropTypes
tags: phase-3 phase-3-fe react
---

Today we looked at how to upload files from React and how to add PropTypes to your components to help prevent bugs and give type hints.

On uploading files, we showed one method of doing it that _does not_ involve sending HTML form data, but instead sending binary data. This introduced an issue with the back-end not accepting our request because it had the `Content-Disposition` header. This was resolved, but I'm putting it here as a reminder.

We also had to deal with refs for the first time in order to access the file field from the front-end.

I have looked and looked and it seems no one has ever written how to upload a file as binary data via axios, so here's some sample code. Yours will differ -- you will need the right URL and to add the Authorization header.

```js
// Assumption: you have `file`, which you've gotten from a file
// input element. If the element is `el`, the code to do so looks
// like: `const file = el.files[0]`

axios.put(url, file, {
  headers: {
    'Content-Type': file.type,
    'Content-Disposition': `attachment; filename=${file.name}`
  }
})
```

## Resources

- [Uncontrolled components](https://reactjs.org/docs/uncontrolled-components.html)
- [Refs and the DOM](https://reactjs.org/docs/refs-and-the-dom.html) - class-based version of this
- [useRef hook](https://reactjs.org/docs/hooks-reference.html#useref)
- [Using files from web applications](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)
- [Commit where we added file upload](https://github.com/momentum-team-4/example--family-app-react/commit/8b49b85b1d8e7b016fe0745f59b1d3c3e3f50e7f)
- [Typechecking with PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)
- [Commit where we added PropTypes](https://github.com/momentum-team-4/example--family-app-react/commit/ab0b924085bc8db54c9c605d1e11e8a62238b122)
