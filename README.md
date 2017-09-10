# PHP-Unsplash-Embed-Photos
Embed your Unsplash photos with this easy-bake PHP snippet.

```
<?php 
// The Unsplash API URL that we want to GET.
// Get YOUR_APPLICATION_ID here:
// https://unsplash.com/developers
$url = 'https://api.unsplash.com/users/smpetrey/photos/?client_id=YOUR_APPLICATION_ID';

// Use file_get_contents to GET the URL in question.
// the True parameter makes this array as associative.
$contents = json_decode(file_get_contents($url), TRUE);

// If $contents is not a boolean FALSE value.
if($contents !== false) {
  // Print out the contents.
  foreach($contents as $item) {

    echo $item['urls']['regular'];
    echo $item['links']['html'];
    // echo the array of the item, useful for debugging and traversing an array.
    echo '<pre>'; var_dump($item);
  }
}
?>
```
