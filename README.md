<h1>If URL contains... (in php)</h1>

<h3>How to create condition.</h3>

<p>First, add the following to the top of your PHP document:</p>

```
$ifURL = 'http://' . $_SERVER['SERVER_NAME'] . $_SERVER['REQUEST_URI'];
```

<p>Next, create a variable with your condition.</p>

```
$onMediaPages = ( (strpos($ifURL,"?media")) );
```

<p>In the example above, this would target any URLs the contain a query of <em>"?media"</em>.</p>

<p>You can even create multiple conditions if you wish.</p>

```
$onMediaPages = ( (strpos($ifURL,"?media") || preg_match('/\/media\//', $ifURL)) );
```

<p>In the example above, this would target any URLs that contain a query of <em>"?media"</em>, as well as any URLs that contain <em>"/media/"</em></p>

<p>From there, you use the condition like so:</p>

```
<?php
  if($onMediaPages) {
    echo "Yup! You're on a media page!";
  }
?>
```

<p>Done!</p>
