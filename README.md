## Download or export source trunk from repository (recommended).
- 1. Unzip into web server root directory.
- 2. Edit config.php.
- 3. Edit example.html header to point to your jQuery location
- 4. It's done. Open http://your-server/bitly/example.html in your web browser.

Now look at some usage examples:


summary Usage examples
labels Featured,Phase-Deploy

===JavaScript usage===

Include jQuery library and plugin files in your header.

    <script type="text/javascript" src="/bitly/jquery.bitly.js"></script>
    <link rel="stylesheet" type="text/css" href="/bitly/css/styles.css">

Setup.

    // path to bridge
    $.fn.bitly.defaults.url = '/bitly/bitly.php';

Some examples.

    // shorten every (shortable) URL in <textarea class="message"></textarea>
    $('textarea.message').shortenUrl();
  
    // hook yourInfoHandler to previewable links
    $('a.previewable').addPreview(yourInfoHandler);
  
    // pass info about link address to yourInfoHandler
    $('a#link').bitly('info', yourInfoHandler);


===PHP usage:===

You may also use Bitly class alone on your server side.

    <?php
    include('bitly/lib/bitly.class.php');
    $bitly = new Bitly($your_login, $your_apiKey);
    // pass message containing any number of long (or short) URLs.
    $shortUrl = $bitly->shortenSingle($message);
    ?>
