<a name="1.0.1"></a>
### 1.0.1 (2014-09-11)


#### Bug Fixes

* **gruntfile:** fixes non bundled library distributable ([2ca6bfb6](http://github.com/angular-platanus/restmod/commit/2ca6bfb6a222ff65fba05f28f6ee175dc8671530), closes [#125](http://github.com/angular-platanus/restmod/issues/125))


<a name="1.0.0"></a>
## 1.0.0 (2014-09-10)


#### Bug Fixes

* **common:** removes promise clearing in `$cancel` ([7cb4ad5b](http://github.com/angular-platanus/restmod/commit/7cb4ad5b0156ec9188d1f7913411c378a69e8867))
* **tests:** changes old notation ([8c4c9d48](http://github.com/angular-platanus/restmod/commit/8c4c9d48fe07817f87179c77159d660505024ddd), closes [#33](http://github.com/angular-platanus/restmod/issues/33))


#### Features

* creates the extended api module that is included in collections and records. ([c05a7b3c](http://github.com/angular-platanus/restmod/commit/c05a7b3c50d764ef57338f3c96d056ac0f354ce7), closes [#78](http://github.com/angular-platanus/restmod/issues/78), [#115](http://github.com/angular-platanus/restmod/issues/115))
* **builder:**
  * define accepts individual implementations for record/collection/type. ([2966a46d](http://github.com/angular-platanus/restmod/commit/2966a46dfdd97555d5dba63f3c68d2d53a087df0))
  * changes the way property renaming is configured, adds the setRenamer method. ([91ab4a33](http://github.com/angular-platanus/restmod/commit/91ab4a339ee7f2c360177bf2cb46d1362d7e37e0), closes [#111](http://github.com/angular-platanus/restmod/issues/111))
* **common:**
  * improves promise chaining using the `$then` method. ([aab2e309](http://github.com/angular-platanus/restmod/commit/aab2e30940553cf49c427dae85126d4547aaabbc))
  * adds the $asPromise method ([3e0dc98d](http://github.com/angular-platanus/restmod/commit/3e0dc98d1dee4e7f7d5e2c7e11a66359738c61aa))
* **model:**
  * adds $mix method to extend a model after being created ([8fce2ec9](http://github.com/angular-platanus/restmod/commit/8fce2ec9399daaf38bb5a719c071ce28d0553deb))
  * makes $inferKey public so it can be overriden. ([22900b4d](http://github.com/angular-platanus/restmod/commit/22900b4dd177c6df6bce32261dcc855bc8ef56c5), closes [#113](http://github.com/angular-platanus/restmod/issues/113))
* **plugins.debounced:** changes use of classDefine variables by configuration variables ([14f76cff](http://github.com/angular-platanus/restmod/commit/14f76cff1d8b3853138589c8116e2c398f7f8fe1))
* **plugins.paged:** changes use of classDefine variables by configuration variables ([5ddc1904](http://github.com/angular-platanus/restmod/commit/5ddc1904a4be7de4c9fcbc55de7980ee99eebff9))
* **utils:**
  * overhaul extendOverriden to be used in factory ([7b309652](http://github.com/angular-platanus/restmod/commit/7b3096523ca5e5418bcb89c308e61edb76bca175))
  * adds assertion method and integrates it ([badc381a](http://github.com/angular-platanus/restmod/commit/badc381a4ccfa1465a1c5d42bbe38f9099af856e))


#### Breaking Changes

* `$then` and `$asPromise` callbacks arguments have changed, `$promise` as public property is deprecated.

$then and $asPromise callbacks will now always receive the related resource as first parameter. Last promise result/rejection reason
will be located in the `$last` property of the resource.

Replace references to `$promise` by calls to `$asPromise()`.
 ([aab2e309](http://github.com/angular-platanus/restmod/commit/aab2e30940553cf49c427dae85126d4547aaabbc))
* CommonApi methods are no longer available at static (class) level
 ([52b2591f](http://github.com/angular-platanus/restmod/commit/52b2591f9bba0084defa6f07f28def3975bff760))
* define and classDefine no longer accept types other than functions.

Replace calls to `define({ /* various methods */ })` by various calls to `define`, same for classDefine.

Replace usage of `classDefine` for type level config variables by proper configuration variables set
using `setProperty`.
 ([2966a46d](http://github.com/angular-platanus/restmod/commit/2966a46dfdd97555d5dba63f3c68d2d53a087df0))
* Renaming has been disabled by default, removed setNameEncoder/setNameDecoder/disableRenaming methods

You must provide a custom renamer if you need renaming now, the idea is use a **style**.

Replace setNameEncoder/setNameDecoder/disableRenaming methods usage setRenamer method.

Closes #111
 ([91ab4a33](http://github.com/angular-platanus/restmod/commit/91ab4a339ee7f2c360177bf2cb46d1362d7e37e0))


<a name="0.18.2"></a>
### 0.18.2 (2014-08-30)


#### Bug Fixes

* **utils:** fixes iframe array type hijack for IE9-IE10 ([ce553426](http://github.com/angular-platanus/restmod/commit/ce55342604c8816600690a66994a5b067378f869))


<a name="0.18.1"></a>
### 0.18.1 (2014-08-30)

#### Features

* **tests:** adds separate karma configuration for sauce ([32d8f815](http://github.com/angular-platanus/restmod/commit/32d8f815271335ad195f443e8d453af934996ea6))
* **utils:** improves array type creation, prefers prototype replacement strategy before ifra ([0b35aa04](http://github.com/angular-platanus/restmod/commit/0b35aa046c95116034a2277c38991214a18f948d), closes [#89](http://github.com/angular-platanus/restmod/issues/89))


<a name="0.18.0"></a>
## 0.18.0 (2014-08-26)


#### Features

* removes trailing slashes from generated urls ([188a7f75](http://github.com/angular-platanus/restmod/commit/188a7f754f345f772be8b4b9a1427972631fb4b6))
* **collection:** unifies interface with record api. ([7fa0b64c](http://github.com/angular-platanus/restmod/commit/7fa0b64ce939ce2f3c9184207e75cbf529bbe690), closes [#63](http://github.com/angular-platanus/restmod/issues/63))


#### Breaking Changes

* collection.$feed is called collection.$decode now.

Closes #63
 ([7fa0b64c](http://github.com/angular-platanus/restmod/commit/7fa0b64ce939ce2f3c9184207e75cbf529bbe690))


<a name="0.17.0"></a>
## 0.17.0 (2014-08-25)


#### Bug Fixes

* **Gruntfile:** couple of syntax errors ([e5c3da47](http://github.com/angular-platanus/restmod/commit/e5c3da47f06158506429229f6c87833bbd6feb4f))
* **default_packer:** changes default links property to li linked ([ad3fa2f9](http://github.com/angular-platanus/restmod/commit/ad3fa2f9b8bb754387ceee1d82710cf5cf7c2069))
* **relations:** fixes default belongsToMany key property to use singularized attribute name ([2d474dea](http://github.com/angular-platanus/restmod/commit/2d474deaaa487d795ad1e4ba02ea0413ad76652d))


#### Features

* adds the default packer! ([e790ef0b](http://github.com/angular-platanus/restmod/commit/e790ef0be0f8c56d3ec39b3b3214e35c10f1227c), closes [#62](http://github.com/angular-platanus/restmod/issues/62))
* adds PackerCache service. ([99d7639f](http://github.com/angular-platanus/restmod/commit/99d7639f1adaed3ae8b18810379cd08e83d0e7da))
* **builder:**
  * changes the __var__ format for model config to all caps VAR format ([decb21e0](http://github.com/angular-platanus/restmod/commit/decb21e07ddf4327dda9c4e753ac2dc9c0f2d578))
  * makes packer a configuration option settable as __packer__ ([fc12bd9d](http://github.com/angular-platanus/restmod/commit/fc12bd9dd64aff9ff2200e0fca1b1863635f8f87))
  * changes model configuration variables name format. ([b0b87e22](http://github.com/angular-platanus/restmod/commit/b0b87e22bedf686eb510f7cb409a530a18fa17a2))
* **docs:** adds the integration guide! ([153caf8e](http://github.com/angular-platanus/restmod/commit/153caf8e6211281de63097fd7fe000747a8b9891), closes [#101](http://github.com/angular-platanus/restmod/issues/101))
* **factory:** adds default value fallback to $getProperty ([da283132](http://github.com/angular-platanus/restmod/commit/da2831329156e8e4080e6d5c4d024cbf8ecf7a40))
* **model:**
  * adds model name inference from url. ([c3ab4819](http://github.com/angular-platanus/restmod/commit/c3ab4819832628733876e763e11a5e06304fe9ba))
  * changes baseUrl property name to url ([e654176a](http://github.com/angular-platanus/restmod/commit/e654176a0811ac02b8f99b5104e5497e32074ffb))
* **packer_cache:** changed to expect plural resource names ([59305f5f](http://github.com/angular-platanus/restmod/commit/59305f5f57119a8ab86c84873c2169214dc79194))


#### Breaking Changes

* renames restmodProvider.pushModelBase method to restmodProvider.rebase


# 0.16.3 (2014-08-19)

## Bug fixes

### serializer

* moves the check for the $ prefix to after the nameDecoder is called. (c0c0f65)

# 0.16.2 (2014-08-18)

## Features

### builder

* adds the belongsToMany relation. (8c368ff)

## Bug fixes

### serializer

* fixes wildcard mapping for decoding and adds missing test (db27cf1)

* encoding failing for null values (4d515c8)

# 0.16.0 (2014-08-14)

## Features

## Builder

* Adds attribute mapping support

## Model

* Adds packer support

* Adds $wrap/$unwrap methods

## Breaking Changes

* Adds query parameter support to $find (193dedc)

* Changes module name to 'restmod'

* Changes service name to 'restmod' and provider name to 'restmodProvider'

# 0.14.0 (2014-05-19)

## Features

### Model

* Adds the `$reveal` method, this methods allows to display before a call to $save succeds.

* Adds the `$moveTo` method, this method is used to change the item position in parent collection even before it is revealed.

## Breaking Changes

* changes the way creation of object in collection work. (7803c90)

* makes `$inferKey` only be called for raw data. (58a2378)

* changes $extend to only copy non-private properties. (5172aa9)

* makes $build use $extend. (c00ea92)


# 0.13.0 (2014-03-14)

## Breaking Changes

* replaces SyncMask by string mask. Use `attr: { ignore: 'CRU' }` in an attribute definition to specify if it should be considered when **C**reating, **U**pdating or **R**eading (d6b39e2)
* makes properties that start with **$** private. Private properties are not consideren when encoding/decoding an object (2549845)

* makes $each method skip private properties (9d36bdd)


# 0.12.0 (2014-01-24)

## Features
### ModelBuilder

* adds the setUrlPrefix builder method. (1cce503)

* adds setPrimaryKey function. (59bc815)

## Breaking Changes

* $build, it no longer allows a private key to be passed directly, for that use $new or $build({ id: X })

# 0.11.1 (2014-01-22)

## Features
### Model

* adds the after-init hook. (f761fec)

# 0.11.0 (2014-01-22)

## Breaking Changes

* removes build hook shorcut methods (`afterCreate`, `afterFeed`, etc ...). Use `on('hook-name', function() {})` instead.

# 0.10.2 (2014-01-22)

## Features
### DirtyModel

* Adds $restore method (652620e)

### Builder

* adds ability to define class methods and hooks in the object definition using special prefixes. (7c26ed5)

# 0.10.1 (2014-01-16)

## Features
### Collection

* adds $indexOf method and makes $remove actually remove something. (0175ae8)

# 0.10.0 (2014-01-15)

## Features

* adds belongsTo relation and improves url generation. (f3bb097)

## Breaking Changes

* replaces the hasMany/hasOne modifiers parameter `alias` by `path`.
* removes the restUrlBuilder and all related functions.

# 0.1.1

* Initial prototype.
