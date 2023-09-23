# Digital Clock

Languages Used

## HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digital Clock</title>
    <link rel="stylesheet" href="./style.css" />
  </head>
  <body>
    <h1>Digital Clock</h1>
    <div id="clickme" class="clock1">12:15:00 AM</div>
    <script src="./index.js"></script>
  </body>
</html>
```

## CSS

```css
.clock1 {
  border: 3px solid red;
  padding: 20px;
  color: red;
  font-size: 50px;
  font-weight: bold;
  margin: auto auto;
  text-align: center;
}
.clock2 {
  border: 3px solid green;
  padding: 20px;
  color: green;
  font-size: 50px;
  font-weight: bold;
  margin: auto auto;
  text-align: center;
}
h1 {
  color: green;
}
```

## JS

```js
// create a digital clock using javascript

function showTime() {
  let Time = new Date();
  let h = Time.getHours();
  let m = Time.getMinutes();
  let s = Time.getSeconds();
  let am_pm = "PM";

  if (h > 12) {
    h = h - 12;
    am_pm = "AM";
  }

  if (h == 0) {
    h = 12;
  }
  h = h < 10 ? "0" + h : h;
  m = m < 10 ? "0" + m : m;
  s = s < 10 ? "0" + s : s;

  let com_time = h + ":" + m + ":" + s + " " + am_pm;
  let x = document.getElementById("clickme");
  if (s >= 30) {
    x.textContent = com_time;
    console.log(x);
  } else {
    x.textContent = com_time;
    x.classList.add("clock2");
    x.classList.remove("clock1");
    console.log(x);
  }
}
setInterval(showTime, 1000);
showTime();
```
