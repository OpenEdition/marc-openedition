.. _overview:

Overview 
============================================

.. contents:: Table of Contents
   :depth: 2

MARC stands for **MA**\ chine **R**\ eadable **C**\ ataloging. This bibliographic metadata format was created by the `Library of Congress <https://www.loc.gov/>`_ to describe its collections and to provide a way to exchange standardized cataloging information between libraries.

Separator characters & graphical representation
------------------------------------------------

MARC records follow a strict structure, consisting of a **leader**, a **directory** and **variable fields**. This structure relies on the use of separator characters called **record terminator**, **field terminator** and **subfield delimiter**. Those non-printing characters are usually graphically represented by other characters in documentations.

Being ISO 2709 compliant, OpenEdition MARC records use ISO 646 IS1, IS2 and IS3 as separator characters:

+--------------+-----------+------------------+--------------------+------------------------+--------------------------+
| ISO 646      | Character | Signification    | MARC record use    | Unicode                | Graphical representation |
+==============+===========+==================+====================+========================+==========================+
| IS1          |    ``US`` | Unit Separator   | Subfield delimiter | ``\u001f``             | ``$``                    |
+--------------+-----------+------------------+--------------------+------------------------+--------------------------+
| IS2          |    ``RS`` | Record Separator | Field terminator   | ``\u001e``             | ``^``                    |
+--------------+-----------+------------------+--------------------+------------------------+--------------------------+
| IS3          |    ``GS`` | Group Separator  | Record terminator  | ``\u001d``             | ``\``                    |
+--------------+-----------+------------------+--------------------+------------------------+--------------------------+

The use of a record terminator character allows to concatenate multiple records in one ``.iso2709`` file without line-break nor carriage return.

MARC fields may be identified by indicators which may contain whitespaces. Indicators whitespaces will be graphically represented in this documentation as underscores (``_``).

Record identification
----------------------

MARC records are identified by a unique identifier, located in field 001 in UNIMARC and MARC21. In OpenEdition records, this identifier is made of three groups of characters, separated by hyphens.

* First group indicates on which OpenEdition platform the resource is located: possible values are OB and OJ, standing for OpenEdition Books and OpenEdition Journals.
* Second group designates whether the publisher (if the resource is a book) or the journal.
* Third group is a numeric identifier for the resource itself. Third group is ommited if the resource is a journal.

Hence, a record of which field 001 is ``OB-pur-49456`` (see example below) would correspond to item ``49456`` published by publisher ``pur`` (Presses Universitaires de Rennes) on OpenEdition Books. Then, matching URL for this resource is https://books.openedition.org/pur/49456

All records issued by OpenEdition are identified by its `cataloging agency code <https://www.loc.gov/marc/organizations/org-search.php>`_ ``FrMaCLE``, standing for **Fr**\ ance - **Ma**\ rseille - **C**\ entre pour **L**\ '**É**\ dition électronique Ouverte. This information is located in field ``040$a`` in MARC21 and in field ``801$b`` in UNIMARC.


Example record
---------------------

For illustrative purposes, here is a Marc21 record from `OpenEdition Books <https://books.openedition.org/pur/49456>`_, with separator characters substituted by their graphical representation and line-breaks added for readability. First line contains leader (first 24 octets) and directory, next lines are variable fields:

.. code-block:: none

	03061    a2200517   4500001001300000003000800013005000900021007001500030008004100045020001800086040001500104041000800119100002200127245007700149260005100226300001500277500001000292520157700302650001501879650001501894650002901909700003001938700002301968700003001991700002102021700002702042700002502069700002402094700002602118700002302144700002102167700002202188700002502210700002502235700004002260700001802300700002102318700002802339700002502367700002302392700002202415700001902437760001402456776001802470856005502488^
	OB-pur-49456^
	FrMaCLE^
	20180306^
	cu ||||||m||||^
	000000e||||||||xx |||||s|||||||||0|fre|d^
	$a9782753559936^
	$aFR-FrMaCLE^
	$afre^
	1 $aBonfante, Larissa^
	00$aÉtrusques$bLes plus heureux des hommes$cDominique Frère, Laurent Hugot^
	$aRennes$bPresses universitaires de Rennes$c2018^
	$a367-XVI p.^
	$aEbook^
	$a« Les plus religieux des hommes. » La célèbre formule de Tite-Live a forgé l’idée d’un peuple étrusque empreint de religiosité et particulièrement attentif au respect des rituels religieux et funéraires. Les tombes aux fresques étonnantes, à l’architecture monumentale et au riche matériel participent à cette vision d’une civilisation soucieuse de vénérer ses dieux et d’honorer ses morts. Mais une civilisation se révèle toujours plus riche et complexe que ce qu’en laissent les témoignages écrits de ceux qui l’ont côtoyée, affrontée sans vraiment la connaître. Pour approcher la réalité quotidienne et spirituelle de ce que fut la vie des Étrusques, loin des stéréotypes qui en font une société figée dans des croyances morbides et des pratiques rituelles contraignantes, il est vital de changer de regard. Il faut observer, embrasser l’immense patrimoine culturel qu’ils nous ont légué avec une curiosité insatiable, une volonté de comprendre au-delà des simplifications et exagérations, des condamnations morales laissées par les Grecs et les Latins.  Ce livre est un hommage à Jean-René Jannot, étruscologue français qui a su avec bonheur transmettre un savoir, une passion pour un peuple si proche par la géographie mais si différent de nous. Le sous-titre « Les plus heureux des hommes » désigne les Étrusques bien-sûr mais aussi toutes celles et tous ceux qui ont eu la chance de travailler avec Jean-René Jannot à la réhabilitation d’une des premières grandes civilisations européennes.^
	4$aAntiquité^
	4$aÉtrusques^
	4$aAnthropologie historique^
	1 $aBouke van der Meer, L.^
	1 $aBriquel, Dominique^
	1 $aCamporeale, Giovannangelo^
	1 $aCherici, Armando^
	1 $aColas-Rannou, Fabienne^
	1 $aGaultier, Françoise^
	1 $aGran-Aymerich, Jean^
	1 $aHaack, Marie-Laurence^
	1 $aHaumesser, Laurent^
	1 $aJolivet, Vincent^
	1 $aJoncheray, Claire^
	1 $aLubtchansky, Natacha^
	1 $aMaffre, Jean-Jacques^
	1 $aMassa-Pairault, Françoise-Hélène^
	1 $aPiel, Thierry^
	1 $aSantrot, Jacques^
	1 $aSantrot, Marie-Hélène^
	1 $aThuillier, Jean-Paul^
	1 $aWhitehead, Jane K.^
	1 $aFrère, Dominique^
	1 $aHugot, Laurent^
	0 $x2111-496X^
	$z9782753534360^
	4 $uhttp://books.openedition.org/pur/49456$yÉtrusques^\
