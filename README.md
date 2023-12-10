# 🎨 Creating an application

At a minimum, an app's metadata is the application's name, description, package ID, and version. A package ID must follow the format of `company.app_name` and must contain no capital letters, spaces, or symbols other than `-` and `_`. A demo application's metadata definition would look like this:

```javascript
meta = {
    /* application name */
    name: 'Demo',
    
    /* application description */
    description: 'cool demo application :3',
    
    /* application icon */
    icon: 'https://placehold.co/400',
    
    /* package id */
    pkg: 'flow.demo',
    
    /* application version */
    version: '1.0.0'
}
```

An application also requires a function to run when the app is opened. The simplest way to show content in an application is the `innerHTML` property on the window's content.

```javascript
async open () {
  const win = window.wm.createWindow({
    title: this.meta.name,
    icon: this.meta.icon,
    width: 700,
    height: 500
  })

  win.content.style.background = 'var(--base)'
  win.content.innerHTML = `
    <h1>Hello World!</h1>
    <p>This is my extra cool demo application.</p>
  `

  return win
}
```

Put these two together by creating  `demoapp.js` in the `Applications` folder for your first application. Inside this file, you're going to define a class with two items inside.

* The `meta` property, which provides the application's metadata to FlowOS.
* The `open` method, which FlowOS will trigger when the application is opened.

The will be inside the "`DemoApp`" in this example, so it can be read by FlowOS.

```javascript
export default class DemoApp {
  meta = {
    name: 'Demo',
    description: 'cool demo application :3',
    icon: 'https://placehold.co/400',
    pkg: 'flow.demo',
    version: '1.0.0'
  }
  
  async open () {
    const win = window.wm.createWindow({
      title: this.meta.name,
      icon: this.meta.icon,
      width: 700,
      height: 500
    })

    win.content.style.background = 'var(--base)'
    win.content.innerHTML = `
      <h1>Hello World!</h1>
      <p>This is my extra cool demo application.</p>
    `

    return win
  }
}
```

That's just about it for a simple application. Later on, you can add your masterpiece to an app repository!
