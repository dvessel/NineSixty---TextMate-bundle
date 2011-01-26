# NineSixty - TextMate bundle

Shortcuts for the [NineSixty Drupal theme](http://drupal.org/project/ninesixty).

## Installation

From the terminal:

    cd Library/Application\ Support/TextMate/Bundles/
    git clone git://github.com/dvessel/NineSixty---TextMate-bundle.git ./ninesixty.tmbundle

Or just download the packaged .tar or .zip file, rename it to ninesixty.tmbundle and drop it into your "Library/Application Support/TextMate/Bundles" folder.

## Usage

Within a theme template:

    'cc'

    <body>
      cc->
     [<div id="" class="container-12/16/24">
        [end focus]
     </div>]
    …

Initial focus will be on the '12/16/24'. Type out a value then tab to select the id. If it isn't needed just delete and tab again to place focus inside the div container. Tabbing after the whole id attribute is selected will place focus within the quotes when you do need to give it an id.

    'gg'

    <div class="container-12">
      gg->
     [<div class="grid-1">
        [end focus]
      </div>]
    …

Focus will be on '1'. Type in a value then tab to place focus inside the div.

    'ns' within the html scope.

    <div class="container-12">
      ns->
     [<div class="<?php print ns('grid/prefix/suffix/push/pull-N', $page[''], N, $page[''], N, $page[''], N, $page[''], N); ?>">
        [end focus]
      </div>]
    …

The ns() function supplied by NineSixty will be setup. Keep entering values and tab through the parameters and delete what isn't needed.

    'ns' within the html class scope.

    <div class="ns->[<?php print ns('grid/prefix/suffix/push/pull-N', $page[''], N, $page[''], N, $page[''], N, $page[''], N); ?>]">
    
If you already have a an element prepared and the cursor is within quotes of the element class, it will insert everything starting with `<?php`.

    'ns' within php scope (tpl.php)

    <div class="<?php print ns->[ns('grid/prefix/suffix/push/pull-N', $page[''], N, $page[''], N, $page[''], N, $page[''], N);] ?>">

    'ns' within php scope (template.php)

    <?php
    function mytheme_preprocess_page(&$vars) {
      …
      $ns_class = ns->[ns('grid/prefix/suffix/push/pull-N', $page[''], N, $page[''], N, $page[''], N, $page[''], N);]
      …
    }

All you really need to remember are 3 triggers but ns changes depending on the context.

Happy theming!
