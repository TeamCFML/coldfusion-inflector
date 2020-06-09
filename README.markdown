# CFML Inflector

This is a CFML (Lucee/Cold Fusion) component which provides the ability to transform words from singular to plural (and back again), capitalises, PascelCase or CamelCases and humanises.  

It is based on a combination of inflector clases openly available under MIT licence.

## Example Usage

Copy the `Inflector.cfc` file somewhere CF can find it, and then:

```cfm
<cfset inflector = createobject("component", "Inflector")>
<cfset plural = inflector.pluralise("person")> <!--- people --->
<cfset singular = inflector.singularise("zombies")> <!--- zombie --->
```

## Pluralisation and Singularisation

Pluralisation and singularisation both take into account:

* Standard grammar rules: the plural is formed by adding `s` to the
  end of the singlar form.
* Special cases: specific cases the occur with some word forms, such
  as `analysis` to `analyses`.
* Irregulars: where the singluar/plural don't follow standard rules,
  e.g. `person` becomes `people`.
* Uncountables: words which are the same in both singular and plural
  form, e.g. `rice`, `money`.

## Other String Functions

* `capitalise()` capitalises the first character in a string: `test` becomes `Test`
  
* `camelCase()` converts a given string to camelCase, with all non-alphanumeric characters stripped: `camel_case` becomes `camelCase`
  
* `PascelCase()` converts a given string to PascelCase, with all non-alphanumeric characters stripped: `pascal_case` becomes `PascelCase`

* `variablise()` converts a string to an underscore-separated list:  `PascelCase` or `camelCase` becomes `camel_case`

* `humanise()` converts a string to a human-readable form:  `PascelCase` or `CamelCase` becomes `Camel Case`

* `pad()` pads a given string with spaces or other characters.

* `isPlural` returns true if the word is plural

* `isSingular` returns if the word is singular

See `test/tests/InflectorTest.cfc` for how other strings are handled.

## Licensing and Attribution

inflector-cfml is the results of a combination of several inflector libraries on github including:

* coldfusion-inflector was originally developed by [Tim Blair](https://github.com/timblair)
* [doctrine inflector](http://www.github.com/doctrine/inflector/)

Released under the MIT license as detailed in the LICENSE file that should be distributed with this library; the source code is [freely available](https://github.com/TeamCFML/coldfusion-inflector).
