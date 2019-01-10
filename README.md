# flysystem-onedrive-sharepoint

[Flysystem](https://flysystem.thephpleague.com/) Adapter for OneDrive and SharePoint using [Microsoft Graph API](https://developer.microsoft.com/en-us/graph).

## Installation

You can install the package via composer:

``` bash
composer require dimasahmad/flysystem-onedrive-sharepoint
```

## Usage

The first thing you need to do is get an authorization token for the Microsoft Graph API. For that you need to create an app on the [Microsoft App Registration Portal](https://apps.dev.microsoft.com/).

``` php
use Microsoft\Graph\Graph;
use League\Flysystem\Filesystem;
use NicolasBeauvais\FlysystemOneDrive\OneDriveAdapter;

$graph = new Graph();
$graph->setAccessToken('EwBIA8l6BAAU7p9QDpi...');

$adapter = new OneDriveSharePointAdapter($graph, 'root');
$filesystem = new Filesystem($adapter);

// Or to use the approot endpoint:
$adapter = new OneDriveAdapter($graph, 'special/approot');
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

- [Dimas Ahmad Eka Putra](https://github.com/dimasahmad)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
