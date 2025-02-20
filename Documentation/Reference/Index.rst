.. include:: /Includes.rst.txt

=============================================
View helper reference
=============================================

Condition/String
================

Contains
--------

Description
~~~~~~~~~~~

`See vhs:condition.string.contains <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Condition/String/Contains.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:condition.string.contains(haystack: haystack, needle: needle, then: 'then', else: 'else')}

Condition/Variable
==================

IsNull
------

Description
~~~~~~~~~~~

`See vhs:condition.variable.isNull <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Condition/Variable/IsNull.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:condition.variable.isNull(variable: variable, then: 'then', else: 'else')}

Core
====

Version
-------

Description
~~~~~~~~~~~

Returns the core version number in the format `M.fff.bbb`. The version `11.5.21` would
result in `11005021`.

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:core.version()}
   {pvh:core.version(as: '_version')}

Format
======

Eliminate
---------

Description
~~~~~~~~~~~

`See vhs:format.eliminate <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Format/Eliminate.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {content -> pvh:format.eliminate(whitespace: true)}
   {pvh:format.eliminate(content: someContent, whitespace: true)}

PregReplace
-----------

Description
~~~~~~~~~~~

`See vhs:format.eliminate <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Format/PregReplace.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:format.pregReplace(subject: subject, pattern: pattern, replacement: replacement)}
   {subject -> pvh:format.pregReplace(pattern: pattern, replacement: replacement)}
   {pvh:format.pregReplace(subject: subject, pattern: pattern, replacement: replacement, as: '_as')}

Replace
---------

Description
~~~~~~~~~~~

`See vhs:format.replace <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Format/Replace.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {content -> pvh:format.replace(substring: 'foo', replacement: 'bar')}
   {pvh:format.replace(content: someContent, substring: 'foo', replacement: 'bar', count: 1)}

Trim
----

Description
~~~~~~~~~~~

`See vhs:format.trim <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Format/Trim.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {content -> pvh:format.trim()}
   {content -> pvh:format.trim(characters: 'ab')}
   {pvh:format.trim(content: someContent)}
   {pvh:format.trim(content: someContent, characters: 'ab')}

Iterator
========

Merge
-----

Description
~~~~~~~~~~~

`See vhs:iterator.merge <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Iterator/Merge.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:iterator.merge(a: a, b: b, useKeys: useKeys, as: 'merged')}
   {pvh:iterator.merge(a: a, b: b, useKeys: useKeys) -> f:format.json()}

Random
------

Description
~~~~~~~~~~~

Select random elements from a coma separated list, array, traversable or query
result.

+-----------+-------------------------------------------------------+----------+
| Parameter | Description                                           | Default  |
+===========+=======================================================+==========+
| subject   | The subject Traversable/Array instance from which to  |          |
|           | select random elements.                               |          |
+-----------+-------------------------------------------------------+----------+
| count     | Number of randomly selected elements to be returned.  | 1        |
+-----------+-------------------------------------------------------+----------+
| shuffle   | Shuffle the selected elements.                        | true     |
+-----------+-------------------------------------------------------+----------+
| as        | Template variable name to assign. If not specified    |          |
|           | the ViewHelper returns the variable instead.          |          |
+-----------+-------------------------------------------------------+----------+

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:iterator.random(subject: someArray, count: 3, as: 'randoms')}
   {someArray -> pvh:iterator.random(count: 3, as: 'randoms')}
   {pvh:iterator.random(subject: someArray, count: 3) -> f:variable(name: 'randoms')}

Transform
=========

Flexform
--------

Description
~~~~~~~~~~~

Transforms flexform data to an array.

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:transform.flexform(data: pi_flexform, as: 'pi_flexform_transformed')}

Variable
========

Get
---

Description
~~~~~~~~~~~

`See vhs:format.trim <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Variable/Get.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {pvh:variable.get(name: 'my.template.var.{index}')}

Set
---

Description
~~~~~~~~~~~

`See vhs:format.trim <https://viewhelpers.fluidtypo3.org/fluidtypo3/vhs/5.0.1/Variable/Set.html>`__

Usage examples
~~~~~~~~~~~~~~

::

   {value -> pvh:variable.set(name: name)}
   {pvh:variable.set(name: name, value: value)}
