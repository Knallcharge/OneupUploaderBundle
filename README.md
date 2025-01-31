OneupUploaderBundle
===================

[![CI](https://github.com/1up-lab/OneupUploaderBundle/workflows/CI/badge.svg)](https://github.com/1up-lab/OneupUploaderBundle/actions)
[![Total Downloads](https://poser.pugx.org/oneup/uploader-bundle/d/total.png)](https://packagist.org/packages/oneup/uploader-bundle)

The OneupUploaderBundle for Symfony adds support for handling file uploads using one of the following JavaScript libraries, or [your own implementation](https://github.com/1up-lab/OneupUploaderBundle/blob/main/doc/custom_uploader.md).

* [Dropzone](http://www.dropzonejs.com/)
* [jQuery File Upload](http://blueimp.github.io/jQuery-File-Upload/)
* [Plupload](http://www.plupload.com/)
* [FineUploader](http://fineuploader.com/)
* [FancyUpload](http://digitarald.de/project/fancyupload/) (based on MooTools)
* [MooUpload](https://github.com/juanparati/MooUpload) (based on MooTools)
* [YUI3 Uploader](http://yuilibrary.com/yui/docs/uploader/) (the YUI library is no longer maintained)
* [UploadiFive](http://www.uploadify.com/) ($ 5.00)


Features included:

* Multiple file uploads handled by your chosen frontend library
* Chunked uploads
* Support for: [Gaufrette](https://github.com/KnpLabs/Gaufrette) / [Flysystem](https://github.com/thephpleague/flysystem) / local filesystem
* Provides an orphanage for cleaning up orphaned files
* Supports [Session upload progress & cancelation of uploads](http://php.net/manual/en/session.upload-progress.php) as of PHP 5.4
* Fully unit tested

Documentation
-------------

The entry point of the documentation can be found in the file `docs/index.md`

[Read the documentation for main](https://github.com/1up-lab/OneupUploaderBundle/blob/main/doc/index.md)

Upgrade Notes
-------------
* Version **4.0.0** supports now [Flysystem 2 & 3](https://github.com/1up-lab/OneupFlysystemBundle) (kudos to @[m2mtech](https://github.com/m2mtech)), see [#412](https://github.com/1up-lab/OneupUploaderBundle/pull/412)! Flysystem 1 and OneupFlysystemBundle < 4.0 support was dropped.
* Version **3.2.0** supports now Symfony 6 (kudos to @[pich](https://github.com/pich)), see [#421](https://github.com/1up-lab/OneupUploaderBundle/pull/421)! PHP 7.2/7.3 support was dropped.
* Version **3.0.0** supports now Symfony 5 (kudos to @[steveWinter](https://github.com/steveWinter), @[gubler](https://github.com/gubler), @[patrickbussmann](https://github.com/patrickbussmann), @[ErnadoO](https://github.com/ErnadoO) and @[enumag](https://github.com/enumag), see [#373](https://github.com/1up-lab/OneupUploaderBundle/pull/373)! Symfony 3.x support was dropped.
* Version **2.0.0** supports now Symfony 4 (Thank you @[istvancsabakis](https://github.com/istvancsabakis), see [#295](https://github.com/1up-lab/OneupUploaderBundle/pull/295))! Symfony 2.x support was dropped. You can also configure a file extension validation whitelist now (PR [#262](https://github.com/1up-lab/OneupUploaderBundle/pull/262)).
* Version **1.5.0** supports now [Flysystem](https://github.com/1up-lab/OneupFlysystemBundle) (Thank you @[lsv](https://github.com/lsv)! PR [#213](https://github.com/1up-lab/OneupUploaderBundle/pull/213)) and is no longer compatible with PHP 5.3 (it's [EOL](http://php.net/eol.php) since August 2014 anyway).
* Version **v1.0.0** introduced some backward compatibility breaks. For a full list of changes, head to the [dedicated pull request](https://github.com/1up-lab/OneupUploaderBundle/pull/57).
* If you're using chunked uploads consider upgrading from **v0.9.6** to **v0.9.7**. A critical issue was reported regarding the assembly of chunks. More information in ticket [#21](https://github.com/1up-lab/OneupUploaderBundle/issues/21#issuecomment-21560320).
* Error management [changed](https://github.com/1up-lab/OneupUploaderBundle/pull/25) in Version **0.9.6**. You can now register an `ErrorHandler` per configured frontend. This comes bundled with some adjustments to the `blueimp` controller. More information is available in [the documentation](https://github.com/1up-lab/OneupUploaderBundle/blob/main/doc/custom_error_handler.md).
* Event dispatching [changed](https://github.com/1up-lab/OneupUploaderBundle/commit/a408548b241f47af3539b2137c1817a21a51fde9) in Version **0.9.5**. The dispatching is now handled in the `upload*` functions. So if you have created your own implementation, be sure to remove the call to the `dispatchEvents` function, otherwise it will be called twice. Furthermore no `POST_UPLOAD` event will be fired anymore after uploading a chunk. You can get more information on this topic in the [documentation](https://github.com/1up-lab/OneupUploaderBundle/blob/main/doc/custom_logic.md#using-chunked-uploads).
* Event names [changed](https://github.com/1up-lab/OneupUploaderBundle/commit/f5d5fe4b6f7b9a04ce633acbc9c94a2dd0e0d6be) in Version **0.9.3**, update your EventListener accordingly.

License
-------

This bundle is under the MIT license. See the complete license in the bundle:

    LICENSE

Reporting an issue or a feature request
---------------------------------------

Issues and feature requests are tracked in the [Github issue tracker](https://github.com/1up-lab/OneupUploaderBundle/issues).

When reporting a bug, it may be a good idea to reproduce it in a basic project
built using the [Symfony Standard Edition](https://github.com/symfony/symfony-standard)
to allow developers of the bundle to reproduce the issue by simply cloning it
and following some steps.
