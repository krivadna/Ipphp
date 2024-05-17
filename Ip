<?php
if (!empty($_SERVER['HTTP_CLIENT_IP'])) {
    $ip = $_SERVER['HTTP_CLIENT_IP'];
} elseif (!empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
    
    $ipList = explode(',', $_SERVER['HTTP_X_FORWARDED_FOR']);
    $ip = trim(end($ipList));
} else {
    $ip = $_SERVER['REMOTE_ADDR'];
}

$myfile = fopen("ip.txt", "a") or die("Unable to open file!");
fwrite($myfile, $ip . "\n");
fclose($myfile);

$requestCatcherURL = 'https://a.requestcatcher.com/log?ip=' . urlencode($ip);
file_get_contents($requestCatcherURL);
?>
