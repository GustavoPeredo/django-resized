.. image:: https://github.com/un1t/django-resized/actions/workflows/python-app.yml/badge.svg
    :target: https://github.com/un1t/django-resized/actions/workflows/python-app.yml

Resizes image origin to specified size. Compatible with sorl-thumbnail.

Features
========

- Tested on Django 2.2, 3.0, 3.1, 3.2, 4.0
- Python 3 support

Installation
============

.. code-block:: bash

    pip install django-resized


Configuration (optional)
========================

settings.py

.. code-block:: python

    DJANGORESIZED_DEFAULT_SIZE = [1920, 1080]
    DJANGORESIZED_DEFAULT_QUALITY = 75
    DJANGORESIZED_DEFAULT_KEEP_META = True
    DJANGORESIZED_DEFAULT_FORCE_FORMAT = 'JPEG'
    DJANGORESIZED_DEFAULT_FORMAT_EXTENSIONS = {'JPEG': ".jpg"}
    DJANGORESIZED_DEFAULT_NORMALIZE_ROTATION = True
    

Usage
=====

models.py

.. code-block:: python

    from django_resized import ResizedImageField

    class MyModel(models.Model):
        ...
        image1 = ResizedImageField(size=[500, 300], upload_to='whatever')
        image2 = ResizedImageField(size=[100, 100], crop=['top', 'left'], upload_to='whatever')
        image3 = ResizedImageField(size=[100, 100], crop=['middle', 'center'], upload_to='whatever')
        image4 = ResizedImageField(size=[500, 300], quality=75, upload_to='whatever')
        image5 = ResizedImageField(size=[500, 300], upload_to='whatever', force_format='PNG')

Options
-------


- **size** - max width and height, for example [640, 480]
- **crop** - resize and crop. ['top', 'left'] - top left corner, ['middle', 'center'] is center cropping, ['bottom', 'right'] - crop right bottom corner.
- **quality** - quality of resized image 0..100, -1 means default
- **keep_meta** - keep EXIF and other meta data, default True
- **force_format** - force the format of the resized image, available formats are the one supported by `pillow <http://pillow.readthedocs.io/en/3.4.x/handbook/image-file-formats.html>`_, default to None


How to run tests
================

.. code-block:: bash

    pip install tox
    tox
