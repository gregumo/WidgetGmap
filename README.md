Victoire DCMS Google Maps Bundle
============

##What is the purpose of this bundle

This bundles gives you access to the *Google Maps Widget*.
This widget can put a dynamic Google Maps within your website with the following settings :

* Latitud
* Longitud
* Map's zoom
* Title of the Map
* Hide or not the pointer
* Import of any KML File

##Set Up Victoire

If you haven't already, you can follow the steps to set up Victoire *[here](https://github.com/Victoire/victoire/blob/master/setup.md)*

##Install the bundle

Run the following composer command :

    php composer.phar require friendsofvictoire/gmap-widget

###Reminder

Do not forget to add the bundle in your AppKernel !

```php
    class AppKernel extends Kernel
    {
        public function registerBundles()
        {
            $bundles = array(
                ...
                new Victoire\Widget\GmapBundle\VictoireWidgetGmapBundle(),
            );

            return $bundles;
        }
    }
```

### Parameters
Add your api key in your app parameters

```yaml
    victoire_widget_gmap.api_key: xxx
```

##KML

The widget generate a bug if the KML file is upload on a local project.
You can test KML import with this [example](https://developers.google.com/maps/documentation/javascript/examples/layer-kml) given by Google.

##Multiple widget & Google Maps API

If you use several widgets Google Maps on the same page, in order to prevent each one of them to make Google Maps API call, a javascript is used to call once and for all thhe API.
This javascript triggers an event with only one Google Maps callback to initialize the widgets.

