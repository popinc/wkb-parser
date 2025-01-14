Geo I/O WKB Parser
==================

[![Build Status](https://github.com/geo-io/wkb-parser/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/geo-io/wkb-parser/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/geo-io/wkb-parser/badge.svg?branch=main&service=github)](https://coveralls.io/github/geo-io/wkb-parser?branch=main)

A parser which transforms
[Well-known binary (WKB)](http://en.wikipedia.org/wiki/Well-known_text#Well-known_binary)
representations into geometric objects.

```php
class MyFactory implements GeoIO\Factory
{
    public function createPoint($dimension, array $coordinates, $srid = null)
    {
        return MyPoint($coordinates['x'], $coordinates['y']);
    }

    // ...
}

$factory = MyFactory();
$parser = new GeoIO\WKB\Parser\Parser($factory);

$myPoint = $parser->parse('000000000140000000000000004010000000000000'); // POINT(2.0 4.0)
```

Installation
------------

Install [through composer](http://getcomposer.org). Check the
[packagist page](https://packagist.org/packages/geo-io/wkb-parser) for all
available versions.

```bash
composer require geo-io/wkb-parser
```

License
-------

Geo I/O WKB Parser is released under the [MIT License](LICENSE).
