class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

# Research Data Management Organiser

## Fortgeschrittene Themen

---

Die Bereitstellung dieser Folien wurde von der [Universität Potsdam](https://www.uni-potsdam.de/), dem [Zuse-Institut Berlin (ZIB)](https://www.zib.de) und der [ZB MED](https://www.zbmed.de/) ermöglicht. Sie können frei nachgenutzt werden.

Es gilt die [CC0 1.0 Universell (CC0 1.0) Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/deed.de).

Die Folien sind mit [remark.js](https://remarkjs.com/) erstellt. Der Quellcode der Folien kann über GitHub abgerufen werden: https://github.com/jochenklar/rdmo-advanced.

---

## Inhalt

* Block 1: **Content-Management I**
    * Fragenkataloge, Attribute und Optionen
* Block 2: **Content-Management II**
    * Bedingungen, Ansichten und Aufgaben
* Block 3: **Schnittstellen und Austausch**
    * Import und Export, API, Plugins
* Block 4: **Administration und Konfiguration**
    * Django-Admin Interface, Updates, App, Authentifizierung, Themes
---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Content-Management

### Fragenkataloge, Attribute und Optionen

---

### Fragenkataloge

.center.w66[
    ![](img/fig/question.svg)
]

* Das **strukturierte Interview** wird mithilfe von Katalogen, Abschnitten, Fragensets und Fragen konfiguriert. Eine **Instanz** von RDMO kann mehrere Kataloge haben. Für ein Projekt muss einer dieser Kataloge ausgewählt werden (kann aber gewechselt werden).
* Die Eingaben werden als **Wert** mit der Referenz auf ein **Projekt** und ein **Attribut** gespeichert. Damit bleibt bei einem Wechsel des Katalogs der Wert erhalten.

---

### Fragenkataloge

.screen-img[
    ![](img/screens/questions-management.png)
]

.screen-text[
* Fragenkataloge werden über ein eigenes Interface editiert
* Admins und die Gruppen *Editor* und *Reviewer* haben Zugriff
* Kataloge, Abschnitte, Fragensets und Fragen können erstellt, editiert, kopiert, exportiert und importiert werden
* Alle Elemente verfügen über eine *URI* um sie global identifizierbar zu machen
]

---

### Fragenkataloge

* Kataloge sind nur zugänglich für die User, wenn das **Verfügbar**-Flag gesetzt ist.
* Kataloge können auf spezielle Gruppen und Sites (im Multi-Site-Setup) eingeschränkt werden.
* Kataloge können bei laufenden Projekten durch die User umgeschaltet werden. Werte zu Attributen, die dann keine Frage mehr haben, bleiben erhalten.
* Abschnitte, Fragensets und Fragen können auch in andere Fragenkataloge kopiert werden. So können Fragenkataloge zusammengebaut werden.

---

### Fragen

.screen-img[
    ![](img/screens/questions.png)
]

.screen-text[
* Fragen werden immer einem Fragenset zugeordnet
* Es stehen verschiedene Widget-Typen zur Verfügung (Text, Textfeld, Select-Dropdown, ...)
* Wenn Fragen als *Sammlung* markiert werden, können mehrere Antworten eingegeben werden
]

---

### Fragen

.screen-img[
    ![](img/screens/questions-edit.png)
]

.screen-text[
* Alle Elemente in RDMO haben einen URI Prefix, einen Schlüssel und können einen Kommentar haben
* Elemente können gesperrt werden, um nicht aus Versehen geändert zu werden
* Fragen müssen einem Attribut zugeordnet sein und ein Widget-Type und einen Wert-Typ haben
* Andere Angaben sind optional
]

---

### Fragen

.screen-img[
    ![](img/screens/questions-languages.png)
]

.screen-text[
* Frage und Hilfetext werden per Sprache editiert
* Anzeigenamen werden für Buttons verwendet (z.B. "Schlagwort hinzufügen")
* Im Hilfetext kann Markdown verwendet werden, z.B. `[Text](Link)` für Links, Tooltips können mit der speziellen Syntax `[Text]{Tooltip}` erstellt werden
]

---

### Fragen

**Standardwerte**

* Für Fragen können Standardwerte als Text oder als Option vorgegeben werden.
* Der Standardwert wird für die Nutzenden initial angezeigt, und beim erstmaligen Speichern übernommen.

**Optionale Fragen**

* Fragen können als optional markiert werden und werden dann entsprechend für die Nutzenden markiert.

**Datei-Upload**

* Es können Datei-Uploads konfiguriert werden, um zusätzliches Material wie Grafiken oder Dokumente hochzuladen. Files werden auf dem Server gespeichert und können via Aufgabe versendet werden.

---

**Mögliche Widget-Typen**

.smaller[
* Text
* Textfelt
* Ja/Nein
* Ankreuzfelder
* Radio Buttons
* Select-Dropdown-Menu
* Autocomplete
* Schieberegler
* Datumspicker
* Datei-Upload

]

.aside[

**Mögliche Wert-Typen**

.smaller[
* Text
* URL
* Ganzzahl
* Kommazahl
* Boolsche Variable
* Datum und Uhrzeit
* E-Mail
* Telefon
* Option
* Datei
]

Wert-Typen sind noch nicht vollständig implementiert. In der Zukunft sollen sie aber zur Validierung eingesetzt werden.
]

---

## Fragensets

.screen-img[
    ![](img/screens/questionsets-edit.png)
]

.screen-text[
* Fragensets sind immer einem Abschnitt zugeordnet
* Fragensets können eigene Hilfetexte haben
* Fragensets können als **Sammlung** markiert sein, dann sollte ein Attribut zugeordnet sein
* Fragensets können **geschachtelt** werden, um Hierarchien abzubilden (z.B. für DataCite)
]

---

### Fragensets (Sammlung)

.center.w66[
    ![](img/fig/questionset.svg)
]

* In Fragensets die als Sammlung markiert sind werden die gleichen Fragen für verschiedene **Sets** (z.B. für verschiedene Datensätze) beantwortet.
* Es *sollte* ein Attribut für das Fragenset-Attribut zugeordnet sein (z.B. `project/dataset/id`).
* Für jedes Set wird ein Wert für das Fragenset-Attribut angelegt.
---

### Fragensets (Sammlung)

.screen-img[
    ![](img/screens/questionsets-collection.png)
]

.screen-text[
* Sets werden mit Hilfe von Tabs dargestellt
* Sets können durch die Nutzenden angelegt, umbenannt und gelöscht werden
]

---

### Fragensets (geschachtelt)

.center.w66[
    ![](img/fig/questionset2.svg)
]

* Fragensets können auch Fragensets zugeordnet sein, um Hierarchien abzubilden.
  * z.B. bei DataCite: Datensatz - Creator - Affiliation
* Fragensets in Fragensets können, müssen aber keine Sammlungen sein.

---

### Fragensets (geschachtelt)

.screen-img[
    ![](img/screens/questionsets-nested.png)
]

.screen-text[
* Geschachtelte Fragensets werden vertikal untereinander dargestellt
* Geschachtelte Fragensets die als Sammlung markiert sind verfügen über eigene Buttons zum Erstellen und Löschen von Sets.
]

---

### Domänenmodell und Attribute

* RDMO nutzt ein internes Vokabular aus einem Baum aus `keys`, ähnlich einer Verzeichnisstruktur:
  * `project`
  * `project/dataset`
  * `project/dataset/format`
* Die Attribute verbinden Fragen, Antworten (Werte), Ansichten, Aufgaben, API etc.
* Für neue Fragen müssen in der Regel zunächst neue Attribute geschaffen werden.
* Derzeitige Attribute sind [Kerndatensatz Forschung](https://www.kerndatensatz-forschung.de/), [CERIF](https://www.eurocris.org/cerif/main-features-cerif), [CASRAI](https://dictionary.casrai.org/Category:Terms), [FOAF](http://xmlns.com/foaf/spec/) motiviert.
* Herausforderungen: Weiterentwicklung, logische Konsistenz, Migrationen, Konformität mit [maDMP](https://www.rd-alliance.org/rda-working-groups-solutions-dmp-recording-and-slides-webinar-now-available-0)/[DataCite](https://schema.datacite.org/meta/kernel-4.1/)/[RADAR](https://www.radar-service.eu), Organisation des Community-Prozesses.
* **Domänenmodell sollte zwischen RDMO Instanzen kompatibel bleiben!**

---

### Attribute

.screen-img[
    ![](img/screens/domain-management.png)
]

.screen-text[
* Attribute werden im Domäne-Management verwaltet
* Wie zuvor haben Admins und die Gruppen *Editor* und *Reviewer* Zugriff
* Attribute können erstellt, editiert, kopiert, exportiert und importiert werden
]

---

### Attribute

.screen-img[
    ![](img/screens/attributes-edit.png)
]

.screen-text[
* Im Prinzip haben außer ihrem Schlüssen keine weiteren Eigenschaften
* Durch Setzen eines Übergeordneten Attributs ergibt sich der Domänen-Baum
]
---

### Optionen

.screen-img[
    ![](img/screens/options.png)
]

.screen-text[
* Optionen dienen dazu, feste Antwortmöglichkeiten für Fragen bereitzustellen
* Sie werden mit Radio Buttons, Ankreuzboxen, Select-Drowdown-Menus oder dem Autocomplete Widget genutzt
]

---

### Optionen

.center.w66[
    ![](img/fig/options.svg)
]

* Einzelne Optionen in Optionensets organisiert, die wiederum Fragen im Fragenkatalog zugeordnet werden. Werte speichern Referenzen auf Optionen.

---

### Optionen

.screen-img[
    ![](img/screens/options-management.png)
]

.screen-text[
* Optionensets und Optionen werden im Optionen-Management verwaltet
* Wie zuvor haben Admins und die Gruppen *Editor* und *Reviewer* Zugriff
* Optionensets und Optionen können erstellt, editiert, kopiert, exportiert und importiert werden
]


---

### Optionensets

.screen-img[
    ![](img/screens/optionsets-edit.png)
]

.screen-text[
* Für Optionensets kann ein Wert für die Reihenfolge angegeben werden, der aber nur für den Fall relevant ist, wenn einer Frage mehrere Optionensets zugeordnet werden.
* Falls **Optionset-Provider** (Plugins für Optionensets) konfiguriert sind können sie dem Optionenset zugeordnet werden
]

---

### Optionen

.screen-img[
    ![](img/screens/options-edit.png)
]

.screen-text[
* Optionen werden immer einem Optionenset zugeordnet
* Wenn **Zusätzliche Eingabe** markiert ist, kann zusätzlicher Freitext eingegeben werden
* Der dargestellte Text wird per Sprache eingegeben
]

---

class: center, middle

##### Pause

---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Content-Management II

### Bedingungen, Ansichten und Aufgaben

---

### Bedingungen

.center.w66[
    ![](img/fig/conditions.svg)
]

* Über Bedingungen können Fragensets übersprungen werden.
* Bedingungen werten zuvor eingegebene Werte für ein Attribut aus.
* Bei mehreren Bedingungen muss nur eine zutreffen (logisches ODER).

---

### Bedingungen für Optionen

.center.w66[
    ![](img/fig/conditions-options.svg)
]

* Es können auch Optionensets ausgelassen werden (bei mehreren Sets pro Frage).

---

### Bedingungen

.screen-img[
    ![](img/screens/conditions-management.png)
]

.screen-text[
* Bedingungen werden in einem separaten Management verwaltet
* Wie zuvor haben Admins und die Gruppen *Editor* und *Reviewer* Zugriff
* Bedingungen können erstellt, editiert, kopiert, exportiert und importiert werden
]


---

### Bedingungen

.screen-img[
    ![](img/screens/conditions-edit.png)
]

.screen-text[
* Bedingungen haben eine **Quelle** (das Attribut das ausgewertet wird), eine **Verknüpfung**, und ein **Ziel**, das entweder ein Freitext oder eine bestimmte Option sein kann.
* Die Bedingung trifft dann zu, wenn im Projekt eine Wert eingegeben wurde, bei dem die Verknüpfung mit dem Ziel wahr ist.
]


---

### Bedingungen

* Bedingungen können Fragensets oder Fragen zugeordnet werden
* Fragensets bei denen die Bedingungen nicht zutreffen werden im Interview übersprungen
* Fragen bei denen die Bedingungen nicht zutreffen werden ausgeblendet

---

### Ansichten

.screen-img[
    ![](img/screens/views.png)
]

.screen-text[
* Ansichten werden genutzt um die Eingaben der Nutzenden in einer anderen Form wieder auszugeben.
* In der Regel wird dies für Datenmanagementplan-Vorlagen von Förderorganisationen genutzt
]

---

### Ansichten

.screen-img[
    ![](img/screens/views-management.png)
]

.screen-text[
* Ansichten werden in einem separaten Management verwaltet
* Wie zuvor haben Admins und die Gruppen *Editor* und *Reviewer* Zugriff
* Ansichten können erstellt, editiert, kopiert, exportiert und importiert werden
* Ansichten können wie Kataloge über das **Verfügbar**-Flag, sowie Gruppen und Sites eingeschränkt werden
]

---

### Ansichten

.screen-img[
    ![](img/screens/views-template.png)
]

.screen-text[
* Für das Editieren der Templates gibt es ein eigenes Modal
* Die Templates der Ansichten werden mit Hilfe der Django Template Syntax in HTML geschrieben
* RDMO spezifische `view_tags` dienen dazu, die Werte des Projektes über ihr Attribut anzusprechen
* Die gerenderten HTML Ansichten können über Pandoc in verschiedene Formate exportiert werden
]

---

### Ansichten

Beispiele für RDMO Template-Code:

```django
The main research question of the project is: {% render_value 'project/research_question/title' %}
```

```django
<p>{% render_value_inline_list 'project/research_question/keywords' %}</p>
```

```django
{% get_set 'project/dataset' as datasets %}
{% for dataset in datasets %}
    <p>
        {% render_set_value dataset 'project/dataset/id' %}
    </p>
{% endfor %}
```

```django
{% get_value 'project/dataset/sharing/yesno' as value %}
{% if value.is_true %}
    This will be only rendered if personal_data resolves to be true.
{% endif %}
```

Mehr Beispiele: https://rdmo.readthedocs.io/en/latest/management/views.html.

---

### Ansichten

* Über [django-mathfilters](https://pypi.org/project/django-mathfilters/) kann auch mit Werten gerechnet werden.
* Ansichten können über [Pandoc](https://pandoc.org/) exportiert werden.
* Für spezielle Layouts können Musterdokumente für `.docx` und `.odt` angelegt werden.
    * <https://rdmo.readthedocs.io/en/latest/configuration/export-formats.html>
* Plugins für frei programmierbare Ansichten sind in Planung.

---

### Aufgaben

.screen-img[
    ![](img/screens/tasks.png)
]

.screen-text[
* Aufgaben haben einen Titel und einen Text und werden mit Bedingungen verknüpft
* Wenn eine der Bedingungen zutrifft, wird die Aufgabe in User-Interface angezeigt
]

---

### Aufgaben

* Der Status einer Aufgabe im Projekt kann durch die User verändert werden.
* Über einen Zeitrahmen können, basierend auf vorhergehenden Werten zu bestimmten Attributen, Anfangs- und Enddaten für eine Aufgabe konfiguriert werden.

* Aufgaben können verschickt werden:
    * an fest konfigurierte und/oder frei wählbare Emailaddressen, oder
    * über eine Integration in ein Projekt-Management-Tool.
* Über Webhooks können externe Services den Status einer Aufgabe in RDMO ändern.
* Integrationen werden über Plugins realisiert (z.Z. GitHub und GitLab).

.ref[
    Dokumentation Email: https://rdmo.readthedocs.io/en/latest/configuration/email.html#send-tasks-via-email  
    Dokumentation Integration: https://rdmo.readthedocs.io/en/latest/configuration/plugins.html#service-providers
]

---

### Aufgaben

.screen-img[
    ![](img/screens/tasks-management.png)
]

.screen-text[
* Aufgaben werden in einem separaten Management verwaltet
* Wie zuvor haben Admins und die Gruppen *Editor* und *Reviewer* Zugriff
* Aufgaben können erstellt, editiert, kopiert, exportiert und importiert werden
* Aufgaben können wie Kataloge über das **Verfügbar**-Flag, sowie Gruppen und Sites eingeschränkt werden
]

---

class: center, middle

##### Pause

---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Schnittstellen und Austausch

---

### XML Export

```xml
<rdmo xmlns:dc="http://purl.org/dc/elements/1.1/">
    <catalog dc:uri="https://rdmorganiser.github.io/terms/questions/rdmo">
        <dc:comment/>
        <order>1</order>
        <title lang="en">RDMO</title>
        <title lang="de">RDMO</title>
    </catalog>
    <section dc:uri="https://rdmorganiser.github.io/terms/questions/rdmo/general">
        <dc:comment/>
        <order>0</order>
        <title lang="en">General</title>
        <title lang="de">Allgemein</title>
    </section>
    ...
</rdmo>
```

* Alle Elemente können über XML Dateien exportiert und importiert werden. Dies kann per Element erfolgen (z.B. ein ganzer Fragenkatalog, aber auch einzelne Fragen).
* URI dient zur Identifikation einzelner Elemente.

---

### RDMO URI

```bash
https://rdmorganiser.github.io/terms/questions/rdmo/general
https://rdmorganiser.github.io/terms/questions/rdmo/technical-classification/data-formats/format

https://rdmorganiser.github.io/terms/domain/project/dataset
https://rdmorganiser.github.io/terms/domain/project/dataset/format

https://rdmorganiser.github.io/terms/views/horizon2020
```

* URI setzt sich zusammen aus `uri_prefix`, der Django "App" und dem `path`.
* `uri_prefix` soll von der Institution frei gewählt werden, muss aber die Form eine URL haben. (Die URI muss aber nicht "auflösen".)
* Von der RDMO Arbeitsgemeinschaft gepflegter Content hat den `uri_prefix` `https://rdmorganiser.github.io/terms/`.
* Der `path` setzt sich (automatisch) aus den `keys` der einzelnen Elemente zusammen.
* Beim Import prüft RDMO anhand der URI ob ein Element schon vorhanden ist.

---

### XML Import

* Import über XML-Upload auf den Management Seiten oder über die Command-Line auf dem Server.

.center.w75.shadow[
    ![](img/screens/import.png)
]

* Import prüft ob das Element mit der `uri` bereits vorhanden ist.
    * Felder vorhandener Elemente werden überschrieben/aktualisiert.
    * Nicht vorhandene Elemente werden neu erstellt.
* Referenzen werden über die `uri` aufgelöst. Das referenzierte Element muss schon vorhanden sein. (Reihenfolge: Domäne, Bedingungen, Optionen, Bedingungen, Rest).

---

### Austausch in der Community

* In der Community entwickelter Content wird durch Projekt / Arbeitsgemeinschaft angenommen und zentral zur Verfügung gestellt.
* GitHub Repository zum Austausch: https://github.com/rdmorganiser/rdmo-catalog
* Issues zu Content-Fragen: https://github.com/rdmorganiser/rdmo-catalog/issues
* Content-Gruppe koordiniert den Austausch der Inhalte:
    * Slack-Channel: *#content*
    * Webkonferenzen an jedem 2. Donnerstag im Monat (und bei Bedarf)
    * Sprecherin: Kerstin Wedlich-Zachodin (KIT)
* Workflow zur Kuration der Inhalte über Pull-Requests und Releases wird z.Z. etabliert.
* Im Bereich `shared` wird Content gesammelt der in der Community erstellt wurde, aber nicht zentral gepflegt wird.

---

### Vorhandene Materialien

* **RDMO:**
    * RDMO Domänenmodell (Startpunkt für alle!), Fragenkataloge (RDMO, RDMO-Kurz, DCC, SNF), Optionen, Bedingungen, Ansichten, Aufgaben
* **fodako:**: Kataloge aus dem DFG Kontext.
* **HeFDI:** Einsteiger:innen-freundlicher Katalog für Servicestellen
* **NFDI4ING:** Fragenkatalog: "Mechanical Engineering" (kein README)
* **EmiMin:** Emissionsminderung in der Nutztierhaltung
* **UB FAU Erlangen Nürnberg:** Eins-zu-Eins Horizon2020 Fragenkatalog, Zusätzliche Fragen aus ["Förderkriterien für Wissenschaftliche Editionen in der Literaturwissenschaft" der DFG](https://www.dfg.de/download/pdf/foerderung/antragstellung/forschungsdaten/foerderkriterien_editionen_literaturwissenschaft.pdf).

---

### Programmierbare JSON API

```bash
curl -X GET -H 'Authorization: Token oojoh3phaighaebiNeiyeeCeiY3Peuv2eitoojoh' \
  https://rdmo.aip.de/api/v1/projects/values/?attribute__path=project/dataset/size/volume
```

```json
[
  {
    "id":10061,
    "project":"https://rdmo.aip.de/api/v1/projects/projects/69/",
    "attribute":"https://rdmo.aip.de/api/v1/domain/attributes/262/",
    "set_index":0,
    "collection_index":0,
    "text":"",
    "option":null,
    "created":"2017-05-29T14:50:20.009917Z",
    "updated":"2017-05-29T14:50:20.009924Z"
  },
  ...
]
```

* API kann lesen und schreiben. Wird auch durch das JavaScript Interface genutzt.
* Swagger UI kann aktiviert werden. [rdmo-client](https://github.com/rdmorganiser/rdmo-client) als Muster-Implementation in Python.

---

## Plugins

* Frei programmierbare Projekt-Exporte und -Importe ([rdmo-plugins](https://github.com/rdmorganiser/rdmo-plugins))
    * [RDA DMP Common Standard for machine-actionable DMP](https://github.com/RDA-DMP-Common/RDA-DMP-Common-Standard) (maDMP)
    * [DataCite XML (Kernel 4.4)](https://schema.datacite.org/meta/kernel-4.4/) für Datensätze
    * [RADAR Metadata JSON](https://www.radar-service.eu/de/radar-schema) für Datensätze
    * Andere lokale Datenquellen (z.B. FIS, easy-Online XML)
* Nutzung fremder APIs (z.B. [re3data.org](https://www.re3data.org/), [rdmo-re3data](https://github.com/rdmorganiser/rdmo-re3data))
* Verwendung großer Thessauri in RDMO (z.B. MeSH mit ~30k Einträgen, [rdmo-mesh](https://github.com/rdmorganiser/rdmo-mesh))
* Aktionen in RDMO stoßen externe Vorgänge an:
  * Aufgaben erzeugen Tickets in Projektmanagementtools (GitLab, GitHub)
  * Nutzung von Django Signals, z.B. externe Archivierung von Snapshots

---

##### Plugins

* Programmierung durch die Betreibenden in der `rdmo-app`.
* Aktivierung in den Settings (`config/settings/local.py`).
* Implementation über die Nutzung von Basisklassen:

```python
from rdmo.projects.exports import Export


class CustomExport(Export):

    def render(self):

        ...

        return HttpResponse(...)
```

* Verbindung zur RDMO Kernfunktionalität durch *Signals* und *Handler*.
* Integration von zusätzlichen Bedienelementen durch *Templates*.
* Bereitstellung auf GitHub: [rdmo-plugins](https://github.com/rdmorganiser/rdmo-plugins), [rdmo-re3data](https://github.com/rdmorganiser/rdmo-re3data), [rdmo-mesh](https://github.com/rdmorganiser/rdmo-mesh).

---

class: center, middle
exclude: true

##### Pause

---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Administration und Konfiguration

---

### Django-Admin

.screen-img[
    ![](img/screens/admin.png)
]

.screen-text[
* Das Django-Framework bietet eine reichhaltige Administrations- (oder kurz Admin-) Schnittstelle, die es erlaubt, die meisten Einträge in der Datenbank direkt zu manipulieren.
* Da RDMO ein eigenes Management Interface mitbringt ist eigentlich nur die Nutzendenverwaltung relevant.
]

---

### Django-Admin

Django `superuser` können prinzipiell alles, `staff` kann sich in das Admin Interface einloggen.

**Gruppen**: `editor` kann editieren, `reviewer` kann lesen, `api` kann über die API auf alle Inhalte zugreifen. Kataloge, Ansichten und Aufgaben können nur für bestimmte Gruppen freigegeben werden. Gruppen können aus LDAP oder Shibboleth übernommen werden.

**Rollen**: User sind `member` einer Site (nur für Multi-Site relevant) und können `manager` sein.
Site-Manager können alle Projekte (einer Site) lesen und schreiben.

**Zusätzliche Felder** dienen der Erweiterung des RDMO internen User-Models (und müssen evtl. bei der Registrierung angegeben werden.).

Für die Nutzung der API können **Tokens** im Admin-Interface erstellt werden.

**Content** und **Nutzerdaten** können auch über das Admin-Interface editiert werden.

---

##### Sites (Websites)

.center.w75.shadow[
    ![](img/screens/sites.png)
]

Normalerweise gibt **ein** Eintrag den Namen (rechts oben in der Navigation) und die URL der RDMO Instanz an. Im Multi-Site-Betrieb können mehrere RDMO Sites auf einem Server und mit einer Datenbank betrieben werden. Kataloge, Ansichten und Aufgaben können dann für bestimmte Sites freigegeben werden. Die Sites verfügen über getrennte `rdmo-app` Verzeichnisse und können verschiedene Themes haben.

---

### App

Jede RDMO-Instanz verfügt über eine lokale `rdmo-app`, zunächst nur zur Konfiguration.

```bash
rdmo-up
├── config
│   ├── settings
│   │   └── local.py
│   ├── urls.py
│   └── wsgi.py
├── env
├── manage.py
├── rdmo_theme
│   ├── static
│   └── templates
├── requirements
├── static_root
└── vendor
```

Es bietet sich an, für lokale Anpassungen eine eigene Django-App zu implementieren, z.B. hier `rdmo_theme`. Die App enthält das Theme, kann aber Logik enthalten. Durch Anpassungen an der `urls.py` können zusätzliche Webseiten hinzugefügt werden.

---

### Multi-Site Installation

* RDMO bietet bei Bedarf eine eingeschränkte Mandantenfähigkeit.
* Über das [Sites Framework](https://docs.djangoproject.com/en/2.2/ref/contrib/sites/) von Django können mehrere RDMO Apps auf der selben Datenbank betrieben werden.
* Über ein geteiltes virtuelles Environment können die Instanzen auch gemeinsam upgedatet werden.
* Die verschiedenen Sites haben unterschiedliche URLs und können unterschiedliche Themes haben (z.B. für verschiedene Hochschulen oder Institute).
* Kataloge, Ansichten und Aufgaben können für einzelne Sites frei gegeben werden.
* User aller Instanzen können sich in allen Instanzen einloggen und zu allen Projekten hinzugefügt werden (Ausname: Shibboleth).

.ref[
    Dokumentation: https://rdmo.readthedocs.io/en/latest/configuration/multisite.html
]

---

### Theme

<style>
.screen-theme img{
    position: absolute;
    display: block;
    bottom: 100px;
    height: 340px;
    box-shadow: 0 0 10px silver;
}
.screen-theme1 img {
    left: 80px;
}
.screen-theme2 img {
    right: 80px;
}
</style>

* Lokale Anpassungen für eigenes *Look and Feel*
* Jedes HTML-Template und jede CSS Datei kann überschrieben werden

.screen-theme.screen-theme1[
    ![Theme1](img/screens/theme1.png)
]
.screen-theme.screen-theme2[
    ![Theme2](img/screens/theme2.png)
]

---

##### Theme

Jedes HTML-Template und jede CSS Datei kann überschrieben werden. Für CSS kann SASS verwendet werden.

```bash
├── static
│   └── core
│       ├── css
│       │   ├── fonts.scss
│       │   ├── footer.scss
│       │   ├── header.scss
│       │   └── variables.scss
│       ├── fonts
│       └── img
└── templates
    ├── core
    │   ├── base_footer.html
    │   ├── base_header.html
    │   ├── base_navigation.html
    │   ├── home_text_de.html
    │   └── home_text_en.html
    └── account
        ├── terms_of_use_de.html
        └── terms_of_use_en.html
```

---

Nutzungsbedingungen
-------------------

.center.w75.shadow[
    ![](img/screens/terms-of-use.png)
]

* Über `ACCOUNT_TERMS_OF_USE = True` in `config/settings/local.py` kann eine Seite zu Nutzungsbedingungen beim Registrieren eingeblendet werden.
* Die Seite wird über das Template `account/terms_of_use_de.html` angepasst.
* Das Zustimmen wird in der Datenbank explizit gespeichert.

---

Overlays
--------

.center.w75.shadow[
    ![](img/screens/overlays.png)
]

* Beim ersten Benutzen der Seite wird ein Tutorial in Form von Overlays angezeigt.
* Die einzelnen Texte können wir alle Templates angepasst werden, z.B. in:
    * `projects/templates/projects/overlays/projects_create_project_de.html`
* Theoretisch können auch neue Seiten mit Overlays versehen werden.

---

### Authentifizierung

* Benutzerkonten mit Registrierung unter Verwendung der `django-allauth`-Bibliothek.
    * "Normaler" Workflow: Registrierung, Validierung, Password zurücksetzen.
    * Accounts von Drittanbietern, über OAUTH2 (z.B. ORCID, GitHub, Google, FB, ...).
* Verwendung einer (schreibgeschützten) Verbindung zu einem (lokalen) LDAP-Server.
    * Gruppen können übernommen werden.
* Installieren eines Shibboleth-Service-Providers neben dem RDMO und Herstellen einer Verbindung zu einem Identity-Provider oder zu einer ganzen Shibboleth-Federation.
    * Gruppen können übernommen werden.
    * Großer Spaß für alle Beteiligten!

`django-allauth` und LDAP können kombiniert werden, Shibboleth nicht (läuft über Apache). Terms of use funktionieren auch nicht mit Shibboleth.

---

### Logging & Management-Scripte

Logging sollte in der `config/settings/local.py` konfiguriert werden:

```bash
/var/log/rdmo/rdmo.log                  # interne, von RDMO implementierte Logs.
/var/log/rdmo/error.log                 # Error-Messages bei Server-Error, auch per Mail an `ADMINS`.
/var/log/gunicorn/access.log            # gunicorn Access-Log (nur für gunicorn-Setup)
/var/log/gunicorn/error.log             # gunicorn Error-Log (nur für gunicorn-Setup)
/var/log/httpd/access.log               # Apache Access-Log (alternativ /var/log/apache2, /var/log/nginx)
/var/log/httpd/error.log                # Apache Error-Log (alternativ /var/log/apache2, /var/log/nginx)
```

Management-Scripte werden in der Virtual-Env mit `python manage.py ...` ausgeführt:

```bash
python manage.py createsuperuser        # erstellt einen Admin (superuser)
python manage.py deploy                 # collectstatic & touch config/wsgi.py
python manage.py download_vendor_files  # Läd JS und CSS Files von den CDN
python manage.py import                 # Importiert RDMO XML File
python manage.py set_uri_prefix         # Setzt uri_prefix für allen Content
python manage.py setup_groups           # Erstellt editor, reviewer und api Gruppen
python manage.py migrate                # Wendet Datenbankmigrationen an
python manage.py collectstatic          # Kopiert statische Files nach static_root
python manage.py upgrade                # Kombiniert download_vendor_files, migrate, collectstatic
```

---

### Updates

RDMO wird zentral verwaltet und über den [Python Package Index](https://pypi.org/project/rdmo/) bereitgestellt. Updates in der Regel durch:

```bash
(env) user$ pip install --upgrade rdmo
```

in der virtuellen Umgebung auf dem Server eingespielt. Danach muss der Webserver neu geladen werden.

```bash
root$ systemctl reload apache2
```

Eventuell (siehe Release-Notes) müssen vorher noch Datenbankmigrationen durchgefürt und/oder statische Dateien gesammelt werden:

```bash
(env) user$ ./manage.py migrate
(env) user$ ./manage.py download_vendor_files
(env) user$ ./manage.py collectstatic
(env) user$ ./manage.py upgrade  # alternativ
```

---

Zusammenarbeit
--------------

<style>
table {
  width: 100%;
}
.seperator {
  height: 15px;
}
</style>

<table>
  <tr>
    <td>Website:</td>
    <td>
      <a href="https://rdmorganiser.github.io">rdmorganiser.github.io</a>
    </td>
  </tr>
  <tr class="seperator"></tr>
  <tr>
    <td>GitHub-Organisation:</td>
    <td>
      <a href="https://github.com/rdmorganiser">github.com/rdmorganiser</a>
    </td>
  </tr>
  <tr class="seperator"></tr>
  <tr>
    <td>Dokumentation:</td>
    <td>
      <a href="http://rdmo.readthedocs.io">rdmo.readthedocs.io</a>
    </td>
  </tr>
  <tr>
    <td>Demo-Instanz:</td>
    <td>
      <a href="https://rdmo.aip.de">rdmo.aip.de</a>
    </td>
  </tr>
  <tr class="seperator"></tr>
  <tr>
    <td>Mailingliste:</td>
    <td>
      <a href="https://www.listserv.dfn.de/sympa/subscribe/rdmo">rdmo@listserv.dfn.de</a>
    </td>
  </tr>
  <tr>
    <td>Twitter:</td>
    <td>
      <a href="https://twitter.com/rdmorganiser">@rdmorganiser</a>
    </td>
  </tr>
  <tr>
    <td>Slack:</td>
    <td>
      <a href="https://rdmo.slack.com">rdmo.slack.com</a>
    </td>
  </tr>
  <tr>
    <td>GitHub-Issues: </td>
    <td>
      <a href="https://github.com/rdmorganiser/rdmo/issues">github.com/rdmorganiser/rdmo/issues</a><br />
    </td>
  </tr>
<tr>
    <td></td>
    <td>
      <a href="https://github.com/rdmorganiser/rdmo/issues">github.com/rdmorganiser/rdmo-catalog/issues</a>
    </td>
  </tr>
  <tr class="seperator"></tr>
  <tr>
    <td>Kontakt: </td>
    <td>
      <a href="mail-to:rdmo@listserv.dfn.de">rdmo@listserv.dfn.de</a>
    </td>
  </tr>
  <tr>
    <td></td>
    <td>
      <a href="mail-to:rdmo-team@listserv.dfn.de">rdmo-team@listserv.dfn.de</a>
    </td>
  </tr>
</table>
