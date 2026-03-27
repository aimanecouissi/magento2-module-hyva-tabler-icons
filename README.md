# AimaneCouissi_HyvaTablerIcons

[![Latest Stable Version](http://poser.pugx.org/aimanecouissi/module-hyva-tabler-icons/v)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons) [![Total Downloads](http://poser.pugx.org/aimanecouissi/module-hyva-tabler-icons/downloads)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons) [![Magento Version Require](https://img.shields.io/badge/magento-~2.4.0-E68718)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons) [![License](http://poser.pugx.org/aimanecouissi/module-hyva-tabler-icons/license)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons) [![PHP Version Require](http://poser.pugx.org/aimanecouissi/module-hyva-tabler-icons/require/php)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons) [![Hyvä Compatibility](https://img.shields.io/badge/hyv%C3%A4-compatible-99004D)](https://packagist.org/packages/aimanecouissi/module-hyva-tabler-icons)

Integrates the **[Tabler Icons](https://tabler.io/icons)** free SVG icon set into **Hyvä Themes**, exposing `outline` and `filled` styles as dedicated `SvgIcons` view models. Browse the included icons in [the SVG directory](https://github.com/aimanecouissi/magento2-module-hyva-tabler-icons/tree/main/view/frontend/web/svg) or preview them at [tabler.io/icons](https://tabler.io/icons).

> This module only includes the **free** Tabler Icons set.

## Installation
```bash
composer require aimanecouissi/module-hyva-tabler-icons
bin/magento module:enable AimaneCouissi_HyvaSvgIcons AimaneCouissi_HyvaTablerIcons
bin/magento setup:upgrade
bin/magento cache:flush
```

## Usage

### In Hyvä PHTML templates

Require the view models for the styles you need and call their helper methods to render icons:
```php
<?php

use AimaneCouissi\HyvaTablerIcons\ViewModel\TablerIconsFilled;
use AimaneCouissi\HyvaTablerIcons\ViewModel\TablerIconsOutline;
use Hyva\Theme\Model\ViewModelRegistry;

/** @var ViewModelRegistry $viewModels */

$tablerIconsOutline = $viewModels->require(TablerIconsOutline::class);
$tablerIconsFilled = $viewModels->require(TablerIconsFilled::class);
?>
```
```php
<?= $tablerIconsOutline->shoppingCartHtml('w-6 h-6', 24, 24, ['aria-label' => 'Cart']) ?>
<?= $tablerIconsFilled->starHtml('w-5 h-5 text-yellow-400', 20, 20, ['aria-hidden' => 'true']) ?>
```

Methods are generated from SVG filenames and fully documented via PHPDoc on each view model, so your IDE can autocomplete them.

### In CMS content

The module registers two icon prefixes for Hyvä `SvgIcons`: `tablericons-outline` and `tablericons-filled`. Icons can be used directly in CMS pages, blocks, and widgets:
```txt
{{icon "tablericons-outline/shopping-cart" classes="inline-block w-6 h-6" width=24 height=24}}
{{icon "tablericons-filled/star" classes="inline-block w-5 h-5 text-yellow-400" width=20 height=20}}
```

## Uninstall
```bash
bin/magento module:disable AimaneCouissi_HyvaTablerIcons
composer remove aimanecouissi/module-hyva-tabler-icons
bin/magento setup:upgrade
bin/magento cache:flush
```

## Changelog

See [CHANGELOG](CHANGELOG.md) for all recent changes, including icon set version updates.

## License

The Tabler Icons SVG icons are created by [Tabler](https://github.com/tabler/tabler-icons) and licensed under [MIT](https://github.com/tabler/tabler-icons/blob/master/LICENSE). Individual brand icons may be subject to their own trademark and usage guidelines. Trademark usage is the responsibility of the end user. Please consult individual brand guidelines before displaying logos in commercial contexts.

This module's source code is separately licensed under [MIT](LICENSE).
