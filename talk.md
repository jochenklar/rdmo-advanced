class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

# RDMO für Fortgeschrittene

### Universität Potsdam, 23.6.2020

#### Jochen Klar

---

## Ablauf

* **09:15 Uhr** Einführung und Organisatorisches, kurze Vorstellungsrunde
* **09:20 - 10:00 Uhr** Block 1: Content-Management
    * Fragen, Optionen und Attribute
* **10:15 - 11:00 Uhr** Block 2: Content-Management
    * Bedingungen, Ansichten und Aufgaben
* **11:15 - 12:00 Uhr** Block 3: Schnittstellen und Austausch
    * Import und Export, API, Plugins
* **12:15 - 13:00 Uhr** Block 4: Administration und Konfiguration
    * Django-Admin Interface, Updates, App, Authentifizierung, Themes
---

Projekt RDMO
------------

<style>
.team {
    text-align: center;
    font-size: 0.6em;
    margin-top: 40px;
}
.team .row {
    height: 180px;
}
.team .item {
  display: inline-block;
  width: 180px;
}
.team img {
    width: 120px;
    height: 120px;

    border-radius: 50%;

    margin-bottom: 10px;
}
.partner {
    text-align: center;
    margin-top: 10px;
}
.partner .item {
    display: inline-block;
    margin-top: 10px;
}
.partner p {
    margin: 0;
}
.partner .item {
    vertical-align: top;
}
.partner .aip img {
    height: 55px;
}
.partner .fhp img {
    margin-left: 20px;
    margin-top: 10px;
    height: 50px;
}
.partner .kit img {
    margin-left: 10px;
    height: 55px;
}
.partner .dfg img {
    margin-left: 40px;
    height: 50px;
}
</style>

2 Projektphasen 2015 - 2020, gefördert von der DFG.

<div class="team">
  <div class="row">
    <div class="item">
      <img src="img/team/enke.jpg" /><br />
      <div>Harry Enke (AIP)</div>
    </div>
    <div class="item">
      <img src="img/team/klar.jpg" />
      <div>Jochen Klar (selbst.)</div>
    </div>
    <div class="item">
      <img src="img/team/kramer.jpg" />
      <div>Claudia Kramer (KIT)</div>
    </div>
    <div class="item">
      <img src="img/team/ludwig.jpg" />
      <div>Jens Ludwig (SPK)</div>
    </div>
    <div class="item">
      <img src="img/team/michaelis.jpg" />
      <div>Olaf Michaelis (AIP)</div>
    </div>
  </div>
  <div class="row">
    <div class="item">
      <img src="img/team/neuroth.jpg" /><br />
      <div>Heike Neuroth (FHP)</div>
    </div>
    <div class="item">
      <img src="img/team/straka.jpg" />
      <div>Janine Straka (FHP)</div>
    </div>
    <div class="item">
      <img src="img/team/ulrich.jpeg" />
      <div>Robert Ulrich (KIT)</div>
    </div>
    <div class="item">
      <img src="img/team/wedlich.jpg" />
      <div>Kerstin Wedlich (KIT)</div>
    </div>
    <div class="item">
      <img src="img/team/wuttke.jpg" />
      <div>Ulrike Wuttke (FHP)</div>
    </div>
  </div>
</div>

.partner[
  .item.aip[
    ![AIP](img/partner/aip_de.svg)
  ]
  .item.fhp[
    ![FHP](img/partner/fhp.svg)
  ]
  .item.kit[
    ![KIT](img/partner/kit.svg)
  ]
  .item.dfg[
    ![DFG](img/partner/dfg.jpg)
  ]
]

---

## RDMO Arbeitsgemeinschaft

**Steuerungsgruppe**

* Koordiniert die Weiterentwicklung von RDMO
* Sprecher: Harry Enke (AIP), Gerald Jagusch (UB Darmstadt)
* *Memorandum of Understanding* in Arbeit

**Softwaregruppe**

* Koordiniert die Weiterentwicklung der Software
* Sprecher: Jochen Klar, Slack: *#development*, GitHub: [rdmo](https://github.com/rdmorganiser/rdmo), [rdmo-app](https://github.com/rdmorganiser/rdmo-app), [rdmo-plugins](https://github.com/rdmorganiser/rdmo-plugins)

**Content-Gruppe**

* Koordiniert die Weiterentwicklung von Fragenkatalogen, Domänenmodell, etc.
* Sprecher: Kerstin Wedlich-Zachodin (KIT), Slack: *#content*, GitHub: [rdmo-catalog](https://github.com/rdmorganiser/rdmo-catalog)

---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Content-Management

---

## Content-Management

Fragenkataloge (mit Abschnitten, Fragensets, Fragen), Attribute, Optionensets (mit Optionen), Bedingungen, Ansichten und Aufgaben werden in RDMO allgemein als **Content** bezeichnet und können über das **Management-Menü** durch Admins und Mitglieder der *Editor* Gruppe editiert werden. Mitglieder der *Reviewer* Gruppe können die Management Interfaces ansehen, aber nichts ändern.

.center.w75.shadow[
    ![](img/screen/management.png)
]

---

### Fragenkataloge

.center.w66[
    ![](img/fig/question.svg)
]

* Das **strukturierte Interview** wird mithilfe von Katalogen, Abschnitten, Fragensets und Fragen konfiguriert. Eine einzelne Installation von RDMO kann mehrere Kataloge haben. Für ein Projekt muss einer dieser Kataloge ausgewählt werden.
* Die Eingaben werden als Wert mit der Referenz auf ein Projekt und ein Attribut gespeichert.

???

Ein Katalog besteht aus einer Reihe von Abschnitten, die ihrerseits Fragensets enthalten, die wiederum Fragen enthalten. Abschnitte dienen zur Gliederung, Fragensets entsprechen Seiten im strukturierten Interview. Eine Frage hat einen Text, der dem Benutzer in Fettdruck angezeigt wird, und einen optionalen Hilfetext. Sie hat auch einen Widget-Typ, der bestimmt, welches Schnittstellen-Widget dem Benutzer präsentiert wird (z.B. Textfeld, Auswahlfeld, Radio-Buttons) und kann eine Einheit haben, z.B. Euro.

---

#### Fragen-Management

.center.w75.shadow[
    ![](img/screen/questions.png)
]

---

##### Einfache Fragen

.center.w75.shadow[
    ![](img/screen/question1-screen.png)
]

---

##### Einfache Fragen

.center.w75.shadow[
    ![](img/screen/question1-modal1.png)
]

---

##### Einfache Fragen

.center.w75.shadow[
    ![](img/screen/question1-modal2.png)
]

---

#### Frage mit mehreren Antworten

.center.w75.shadow[
    ![](img/screen/question1-screen.png)
]

---

##### Frage mit mehreren Antworten

.center.w75.shadow[
    ![](img/screen/question2-modal1.png)
]

---

##### Frage mit mehreren Antworten

.center.w75.shadow[
    ![](img/screen/question2-modal2.png)
]

---

##### Frage mit mehreren Antworten

.center.w75.shadow[
    ![](img/screen/question1-screen.png)
]

---

#### Widget-Typ

* Text
* Textarea
* Yes/No
* Checkboxes
* Radio buttons
* Select drop-down
* Range slider
* Date picker

.aside[

#### Wert-Typ

* Text
* URL
* Integer
* Float
* Boolean
* Datetime
* Option

]

---

##### Fragensets mit Tabs

.center.w66[
    ![](img/fig/questionset.svg)
]

* Fragensets mit Tabs haben ein Fragenset-Attribut zugeordnet (z.B. `project/dataset`).
* Es *sollte* ein `id` Attribut für das Fragenset-Attribut existieren (z.B. `project/dataset/id`).
* Für jedes Set wird ein Wert für das `id`-Attribut angelegt.
* Intern haben Werte haben ein `collection_index` Feld für Fragen mit mehreren Antworten und ein `set_index` Feld für Fragensets mit Tabs.

---

#### Fragensets

.center.w75.shadow[
    ![](img/screen/questionset1-modal.png)
]

---

#### Fragensets mit Tabs

.center.w75.shadow[
    ![](img/screen/questionset2-screen.png)
]

---

##### Fragensets mit Tabs

.center.w75.shadow[
    ![](img/screen/questionset2-modal1.png)
]

---

##### Fragensets mit Tabs

.center.w75.shadow[
    ![](img/screen/questionset2-modal2.png)
]

---

##### Fragensets mit Tabs

.center.w75.shadow[
    ![](img/screen/questionset2-screen.png)
]

---

### Domänenmodell und Attribute

* Internes Vokabular aus einem Baum aus `keys`, ähnlich einer Verzeichnisstruktur:
  * `project`
  * `project/dataset`
  * `project/dataset/format`
* Verbindet Fragen, Antworten (Werte), Ansichten, Aufgaben, API etc.
* Für neue Fragen müssen in der Regel zunächst neue Attribute geschaffen werden.
* Derzeitige Attribute sind [Kerndatensatz Forschung](https://www.kerndatensatz-forschung.de/), [CERIF](https://www.eurocris.org/cerif/main-features-cerif), [CASRAI](https://dictionary.casrai.org/Category:Terms), [FOAF](http://xmlns.com/foaf/spec/) motiviert.
* Überarbeitung nötig (Konformität mit [maDMP](https://www.rd-alliance.org/rda-working-groups-solutions-dmp-recording-and-slides-webinar-now-available-0), [DataCite](https://schema.datacite.org/meta/kernel-4.1/), [RADAR](https://www.radar-service.eu); logische Konsistenz).
* **Domänenmodell sollte zwischen RDMO Instanzen kompatibel bleiben!**

---

#### Attribute

.center.w75.shadow[
    ![](img/screen/domain.png)
]

---

#### Attribute

.center.w75.shadow[
    ![](img/screen/domain-modal.png)
]

---

### Fragen mit Optionen

.center.w75.shadow[
    ![](img/screen/question-option-screen.png)
]

---

### Optionen

.center.w66[
    ![](img/fig/options.svg)
]

* Fragen bekommen Optionensets zugeordnet.
* Werte speichern Referenzen auf Optionen.

---

### Optionen

.center.w75.shadow[
    ![](img/screen/question-option-modal.png)
]

---

### Optionensets

.center.w75.shadow[
    ![](img/screen/optionsets-screen.png)
]

---

### Optionensets

.center.w75.shadow[
    ![](img/screen/optionset-modal.png)
]

---

### Optionen

.center.w75.shadow[
    ![](img/screen/option-modal.png)
]

---

### Bemerkungen

* Fragensets und Fragen können kopiert werden. (Ganze Kataloge in RDMO 1.1.)
* Kataloge sind immer zugänglich für die User, in Zukunft werden sie ein `public`-Flag erhalten um sie zu verbergen.
* Ab RDMO 1.1 wird es möglich sein, Kataloge für Gruppen und Sites einzuschränken.
* Kataloge können bei laufenden Projekten durch die User umgeschaltet werden. Werte zu Attributen, die dann keine Frage mehr haben, bleiben erhalten.
* Hilfetexte von Fragen und Fragensets können Markdown-Syntax verwenden.
* Eingaben zu Fragen werden (noch) nicht inhaltlich validiert.
* Fragen können (noch) nicht als optional oder verpflichtend markiert werden.

---

class: center, middle

##### Pause

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

.center.w75.shadow[
    ![](img/screen/conditions.png)
]

---

### Bedingungen

.center.w75.shadow[
    ![](img/screen/condition-modal.png)
]

---

### Bedingungen für Fragensets

.center.w75.shadow[
    ![](img/screen/questionset-condition-modal.png)
]

---

### Ansichten

.center.w75.shadow[
    ![](img/screen/views-screen.png)
]

---

### Ansichten

.center.w75.shadow[
    ![](img/screen/view-screen.png)
]

---

### Ansichten

.center.w75.shadow[
    ![](img/screen/view-modal.png)
]

---

### Ansichten

* Ansichten werden in der Django Template Syntax geschrieben.
* Zusätzlich dienen RDMO spezifische `view_tags` dazu die Werte des Projektes anzusprechen.
    * <https://rdmo.readthedocs.io/en/latest/management/views.html>
* Über [django-mathfilters](https://pypi.org/project/django-mathfilters/) kann auch mit Werten gerechnet werden.
* Ansichten können über [Pandoc](https://pandoc.org/) exportiert werden.
* Für spezielle Layouts können Musterdokumente für `.docx` und `.odt` angelegt werden.
    * <https://rdmo.readthedocs.io/en/latest/configuration/export-formats.html>

---

#### Template-Code

```django
The main research question of the project is: {% render_value 'project/research_question/title' %}
```

```django
<p>
    {% render_value_inline_list 'project/research_question/keywords' %}
</p>
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

### Aufgaben

.center.w75.shadow[
    ![](img/screen/tasks.png)
]

---

### Aufgaben

.center.w75.shadow[
    ![](img/screen/task-modal.png)
]

---

### Aufgaben

.center.w75.shadow[
    ![](img/screen/task-condition.png)
]

---

### Aufgaben

.center.w75.shadow[
    ![](img/screen/task-timeframe.png)
]

---

### Aufgaben

* Aufgaben sind noch nicht vollständig implementiert und bieten derzeit nur geringen Mehrwert.
* Verknüpfung mit Issue-Tracken und Projektmanagement-Software ist in Planung und wird im Herbst 2020 released.

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

* Alle Elemente können über XML Dateien exportiert und importiert werden. Zur Zeit nur grob-granular (Ein Fragenkatalog, alle Optionensets, etc.), ab Herbst 2020 auch einzeln.
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

* URI setzt sich zusammen aus `uri_prefix`, dem RDMO Modul und dem `path`.
* `uri_prefix` soll von der Institution frei gewählt werden, muss aber die Form eine URL haben. (Die URI muss aber nicht "auflösen".)
* Vom RDMO-Projekt erarbeiteter Content hat den `uri_prefix` `https://rdmorganiser.github.io/terms/`.
* Der `path` setzt sich zusammen aus den `keys` der einzelnen Elemente.
* Beim Import prüft RDMO anhand der URI ob ein Element schon vorhanden ist.

---

### XML Import

* Import über XML-Upload auf den Management Seiten oder über die Command-Line auf dem Server.

.center.w75.shadow[
    ![](img/screen/import-screen.png)
]

* Import prüft ob das Element mit der `uri` bereits vorhanden ist.
    * Felder vorhandener Elemente werden überschrieben/aktualisiert.
    * Nicht vorhandene Elemente werden neu erstellt. `path` muss aber "unique" bleiben.
* Referenzen werden über die `uri` aufgelöst. Referenziertes Element muss schon vorhanden sein. (Reihenfolge: Domäne, Bedingungen, Optionen, Bedingungen, Rest).

---

### Austausch in der Community

* In der Community entwickelter Content wird durch Projekt / Arbeitsgemeinschaft angenommen und zentral zur Verfügung gestellt.
* GitHub Repository zum Austausch: https://github.com/rdmorganiser/rdmo-catalog
* Issues zu Content-Fragen: https://github.com/rdmorganiser/rdmo-catalog/issues
* Content-Gruppe koordiniert den Austausch der Inhalte:
    * Slack-Channel: *#content*
    * Webkonferenzen
    * Sprecherin: Kerstin Wedlich-Zachodin
* Workflow zur Kuration der Inhalte ist noch nicht etabliert.

---

### Vorhandene Materialien

* **RDMO Projekt**:
    * RDMO Domänenmodell (Startpunkt für alle!), Fragenkataloge (RDMO, RDMO-Kurz, DCC, SNF), Optionen, Bedingungen, Ansichten, Aufgaben
* **fodako**
    * Unterkataloge: "DFG", "Soziologie + DFG", "Ökonomie + DFG", "Bildungswissenschaften + DFG", "Alle Fragen"
* **NFDI4ING**
    * Fragenkatalog: "Mechanical Engineering" (kein README)
* **UB FAU Erlangen Nürnberg**
    * Eins-zu-Eins Horizon2020 Fragenkatalog
    * Zusätzliche Fragen aus ["Förderkriterien für Wissenschaftliche Editionen in der Literaturwissenschaft" der DFG](https://www.dfg.de/download/pdf/foerderung/antragstellung/forschungsdaten/foerderkriterien_editionen_literaturwissenschaft.pdf).

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

*(in der Entwicklung)*

* Frei programmierbare Projekt-Exporte und -Importe
    * [RDA DMP Common Standard for machine-actionable DMP](https://github.com/RDA-DMP-Common/RDA-DMP-Common-Standard) (maDMP)
    * [DataCite XML (Kernel 4.3)](https://schema.datacite.org/meta/kernel-4.3/) für Datensätze
    * [RADAR Metadata JSON](https://www.radar-service.eu/de/radar-schema) für Datensätze
    * Andere lokale Datenquellen (z.B. FIS, easy-Online XML)
* Nutzung fremder APIs (z.B. [re3data.org](https://www.re3data.org/))
* Aktionen in RDMO stoßen externe Vorgänge an:
  * Aufgrabe erzeugen Tickets in Projektmanagementtools (Jira, Redmine, OTRS)
  * Snapshots werden extern archiviert

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
* Bereitstellung auf GitHub: [rdmo-plugins](https://github.com/rdmorganiser/rdmo-plugins) (analog zu [rdmo-catalog](https://github.com/rdmorganiser/rdmo-catalog)).

---

class: center, middle

##### Pause

---

class: title, center, middle

.rdmo-logo[
    ![RDMO](img/RDMO-logo.png)
]

## Administration und Konfiguration

---

### Django-Admin

Das Django-Framework bietet eine reichhaltige Administrations- (oder kurz Admin-) Schnittstelle, die es erlaubt, die meisten Einträge in der Datenbank direkt zu manipulieren.

.center.w75.shadow[
    ![](img/screen/admin.png)
]

---

### Django-Admin

Django `superuser` können prinzipiell alles, `staff` kann sich in das Admin interface einloggen.

**Gruppen**: `editor` kann editieren, `reviewer` kann lesen, `api` kann über die API auf alle Inhalte zugreifen. *(ab RDMO 1.1)* Kataloge, Ansichten und Aufgaben können nur für bestimmte Gruppen freigegeben werden. Gruppen können aus LDAP oder Shibboleth übernommen werden.

**Rollen**: *(ab RDMO 1.1)* User sind `member` einer Site (nur für Multi-Site relevant) und können `manager` sein.
Site-Manager können alle Projekte (einer Site) lesen und schreiben.

**Zusätzliche Felder** dienen der Erweiterung des RDMO internen User-Models (und müssen evtl. bei der Registrierung angegeben werden.).

Für die Nutzung der API können **Tokens** im Admin-Interface erstellt werden.

**Content** und *Nutzerdaten* können auch über das Admin-Interface editiert werden.

---

##### Sites (Websites)

.center.w75.shadow[
    ![](img/screen/sites.png)
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
├── rdmo_up
│   ├── static
│   └── templates
├── requirements
├── static_root
└── vendor
```

Es bietet sich an, für lokale Anpassungen eine eigene Django-App zu implementieren, z.B. hier `rdmo_up`. Die App enthält das Theme, kann aber Logik enthalten. Durch Anpassungen an der `urls.py` können zusätzliche Webseiten hinzugefügt werden.

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
    ![Theme1](img/screen/theme1.png)
]
.screen-theme.screen-theme2[
    ![Theme2](img/screen/theme2.png)
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

### Authentifizierung

* Benutzerkonten mit Registrierung unter Verwendung der `django-allauth`-Bibliothek.
    * "Normaler" Workflow: Registrierung, Validierung, Password zurücksetzen.
    * Accounts von Drittanbietern, über OAUTH2 (z.B. ORCID, GitHub, Google, FB, ...).
* Verwendung einer (schreibgeschützten) Verbindung zu einem (lokalen) LDAP-Server.
    * Gruppen können übernommen werden.
* Installieren eines Shibboleth-Service-Providers neben dem RDMO und Herstellen einer Verbindung zu einem Identity-Provider oder zu einer ganzen Shibboleth-Federation.
    * Gruppen können übernommen werden.
    * Großer Spaß für alle Beteiligten!

`django-allauth` und LDAP können kombiniert werden, Shibboleth nicht (läuft über Apache).

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
(env) user$ ./manage.py collectstatic
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
  <tr>
    <td></td>
    <td>
      <a href="mail-to:mail@jochenklar.de">mail@jochenklar.de</a>
    </td>
  </tr>
</table>
