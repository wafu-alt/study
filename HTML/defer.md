아직 연구중

[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-defer](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-defer)

```jsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>

    <script>
      document.write("Hello World! top");
    </script>
    <script src="defer3.js"></script>
    <script src="defer.js" defer></script>
  </head>
  <body>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <script>
      document.write("Hello World! bottom");
    </script>
    <script src="defer2.js"></script>
  </body>
</html>
```
![image](https://user-images.githubusercontent.com/83447120/148229281-81ab16f0-a147-4199-bb7a-0cc87d194b5f.png)
