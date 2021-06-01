# Markdown Preview

This is an extremely simple app that I wrote early on when learning React. Inputted text gets updated live in the Preview section through the use of React hooks and the library Marked.

Check it out [here](https://www.sunkenworld.com/markdown-app). To run it locally: clone the repository, run `npm install` and then `npm run start`.

This project uses an input field that saves the inputted text to the state property `inputText` and updates it on change:

```
<textarea id="editor" value={inputText} onChange={setText} />
```

Then, using the Marked library, the inner HTML of the `preview` div is set to the value of `marked(inputText)`.

That's it! It's super simple.

---

Ironically, designing the responsive layout was quite a bit more complex than the primary function of the app. CSS grids were used to accomplish a clean look and responsive functionality. Try resizing the window to see how the headers snap from being written vertically and to the left of the content, to being on top when the viewport gets narrow. This is done by changing the grid template areas when the window reaches a certain minimum width.

And then there's the buttons. The buttons used to expand and collapse the windows use React’s state to set the classes of various elements, as well as change the grid layout. The classes of these divs are set to a value in an array of classes, aptly named `classes`. For example, the `container` div looks like this:

```
<div id="container" className={classes[0]}>
```

If neither the Editor or Preview windows have been expanded, the default class for the `container`, `editor-wrap` and `preview-wrap` divs are set to the classes array:

```
classes = ["container", "editor-wrap", "preview-wrap"];
```

When one of the buttons is clicked to expand or collapse one of the windows, this array will change and therefore the class of each of these divs will change. The rest is handled with CSS styles.

That's just a quick look at some of the code that went into this modest project. If you want to have a peek at the code in full, go to /src/Markdown.js and /src/Markdown.scss.

Please check out my portfolio at https://www.sunkenworld.com/ if you want to see more of my work. Thanks for reading!
