v1.3.1
------

 - If you make your interface `IDisposable`, disposing it will dispose the underlying `HttpClient`
 - If your method return type is `Task<HttpResponseMessage>`, use `HttpCompletionOption.ResponseHeadersRead` instead of `HttpCompletionOption.ResponseContentRead`, allowing you to control if and when the content is read.
 - Add support for the HTTP Patch method
 - Add `[Path(UrlEncode = false)]`, allowing URL encoding to be turned off for individual path parameters
 - Remove the dependency on all of NetStandard.Library (for .NET Core targets)

v1.3.0
------

 - **BREAKING CHANGE**: Add a `RequestQueryParamSerializerInfo` parameter to methods on `IRequestQueryParamSerializer`
 - Add support for specifying `IFormattable` format strings for query parameters, path parameters, and path properties (#21)

v1.2.3
------

 - Allow null BaseAddress on HttpClient
 - Make ApiException constructor public, to allow easier unit testing of RestEase consumers

v1.2.1, v1.2.2
--------------

 - Fix metadata fields in NuGet package (no functional changes)

v1.2.0
------

 - Add support for path properties - path compoments which are the same for every request (#16)
 - Add support for raw, unencoded query parameters (#17)
 - Support query parameters without a key
 - Improve some error messages

v1.1.2
------

 - Avoid dependency on System.Net.Http NuGet package on .NET 4.5

v1.1.1
------

 - Avoid dependency on Microsoft.Net.Http on .NET 4.5

v1.1.0
------

 - Add support for .NET Core (.NET Standard 1.3) - thanks to [Fazouane Marouane](https://github.com/fazouane-marouane)

v1.0.11
-------

 - Fix a test

v1.0.10
-------

 - Do encode '/' in path parameters

v1.0.9
------

 - Encode space as '%20' rather than '+' in path parameters
 - Don't encode '/' in path parameters

v1.0.8
------

 - Fix issue where query parameters not decorated with `[Query]` would always be serialized as ToString, regardless of any `[SerializationMethod]` attributes

v1.0.7
------

 - Handle null paths (e.g. `[Post]` or `[Get(null)]`)

v1.0.6
------

 - Support .NET 4.0 (using Microsoft.Net.Http and Microsoft.Bcl.Async as dependencies)
 - URL Encode path parameters

v1.0.5
------

 - Allow custom serialization of query parameters and query maps
 - Add `[SerializationMethods]` attribute, to specify the default serialization method for bodies and query parameters
 - Move to using a builder pattern for `RestClient`, to make specifying custom serializers/deserializations/configuration easier.
   The old methods are still present, but are marked as deprecated. Please upgrade to the new methods (suggested by the deprecation messages).

v1.0.4
------

 - Fix race condition when creating implementations (#4)

1.0.3
-----

 - Allow interface headers in interface inheritance (#3)
 - Add missing `RestClient.For` overloads

1.0.2
-----

 - Allow interface inheritance (#3)

1.0.1
-----

 - `JsonRequestBodySerializer` sets a default Content-Type header of `application/json`

1.0.0
-----

 - Initial Release