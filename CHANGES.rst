Changes
=======

1.0.1 (unreleased)
-------------------

-

1.0.0 (2022-05-03)
-------------------

- Remove official support for Django < 2.2 and python 2 (it may still works but is untested)
- Added support for Django up to 4.0
- Add support for mirrored orientations #29
- Fix JPEG default quality (fixes #34) #35
- Add 'png' to the formats that need the img mode to be RGBA #39 #41
- Use Image.Resampling.LANCZOS instead of deprecated Image.ANTIALIAS

0.3.11
------

- Check force_format exists before checking value

0.3.10
------

- Improvement: Remove EXIF information without creating new image
- Convert GIF to JPG #19

0.3.9
-----

- Feature: optional manualy setup the extensions for image types in setting DJANGORESIZED_DEFAULT_FORMAT_EXTENSIONS.
- Feature: switch on/off normalize_rotation in setting DJANGORESIZED_DEFAULT_NORMALIZE_ROTATION.
- Fix typo in DJANGORESIZED_DEFAULT_FORCE_FORMAT settings name in code.

0.3.8
-----

- Feature: added force_format.

0.3.7
-----

- Fix: error when orientation exif data is empty.

0.3.6
-----

- Fix: add a deconstruct method.
