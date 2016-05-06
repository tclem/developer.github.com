# developer.github.com

[Nanoc] Dies [nanoc] ist eine Ressource GitHub API gebaut mit. Ziehen Anfragen willkommen!

[pull request] Alle Einreichungen sind willkommen. Um eine Änderung vor, Gabel dieses Repo, verpflichten Sie die Änderungen und senden Sie uns eine (http://help.github.com/send-pull-requests/).

## Entwicklungs

Sie können die aktuellen Abhängigkeiten holen über die Befehlszeile öffnen und läuft `script / bootstrap`:

`` `Sh
$ Script / Bootstrap
==> Installation gem Abhängigkeiten ...
==> Installieren von NPM Abhängigkeiten ...
```

Sie müssen Ruby und Knoten auf dem System installiert. Die erforderlichen Versionen für jede dieser Sprachen in den * .ruby-Version * und * package.json * Dateien bzw. Gefunden werden.

Sie können exec Rake build` laufen `bündeln die Website zu generieren, aber es ist oft nützlicher
Einfach den Server * bauen und * den Ort zur gleichen Zeit starten.

Nanoc kompiliert die Website in statische Dateien in `output` leben. Seine
Klug genug, nicht zu versuchen, unveränderte Dateien zu kompilieren.

Sie können die Website mit `script / server` starten:

`` `Sh
$ Script / server
Laden Standortdaten ...
Kompilieren site ...
[0.28s] erstellen Ausgabe / index.html
[1.31s] erstellen Ausgabe / v3 / Logen / Kommentare / index.html
[1.92s] identische Ausgangs / v3 / logen / index.html
[0.25s] identische Ausgangs / v3 / Fragen / Kommentare / index.html
[0.99s] aktualisieren Ausgabe / v3 / Themen / Labels / index.html
[0.05s] Update Ausgabe / v3 / index.html
…

Site in 5.81s zusammengestellt.
```

Der Standort befindet sich an der `http gehostet: // localhost: 4000`.

[some nice documentation] Nanoc hat (http://nanoc.ws/docs/tutorial/) zum Einstieg. Obwohl, wenn Sie hauptsächlich mit Bearbeiten oder Hinzufügen von Inhalten, werden Sie nicht viel über Nanoc wissen müssen.

[nanoc] : http://nanoc.ws/

## Gestaltungsrichtlinie

Nicht sicher, wie die Dokumentation zu strukturieren? Hier ist, was die Struktur der
API-Dokumentation aussehen sollte:

# API Titel

{:toc}

## API Endpunkt Titel

[VERB] / Path / to / Endpunkt

### Parameter

Name | Typ | Beschreibung
-----|------|--------------
`Name` |` type` | Beschreibung.

### Eingang (Anforderung JSON Körper)

Name | Typ | Beschreibung
-----|------|--------------
`Name` |` type` | Beschreibung.

### Antwort

<%= headers 200, :pagination => default_pagination_rels, 'X-Custom-Header' => "Wert"%>
<%= json :resource_name %>

[Kramdown Markdown extensions] ** Hinweis **: Wir verwenden (http://kramdown.gettalong.org/syntax.html), wie Definitionslisten.

### JSON Antworten

Wir geben die JSON Antworten in Ruby, so dass wir nicht schreiben müssen
Sie mit der Hand ganz über die Dokumentation. Sie können die JSON für eine Ressource machen
So was:

`` `Erb
<%= json :issue %>
```

Das sieht nach oben `GitHub :: Ressourcen :: ISSUE` in` lib / resources.rb`.

Einige Aktionen zurückkehren Arrays. Sie können, indem ein Block die JSON ändern:

`` `Erb
<%= json(:issue) { |hash| [hash] } %>
```

Es gibt auch eine Harke Aufgabe zur Erzeugung JSON-Dateien aus den Musterantworten in der Dokumentation:

`` `Sh
$ Rake generate_json_from_responses
```

Die erzeugten Dateien werden in * json-dump / * enden.

### Klemmenblöcke

Sie können Klemmenblöcke angeben, indem Sie die `Befehls line` Syntax-Hervorhebung verwendet.

`` `Befehlszeilen
$ Curl foobar
```

Sie können bestimmte Zeichen verwenden, wie `$` und `#`, verschiedene Teile zu betonen
Von Befehlen.

`` `Befehlszeilen
# Call foobar
<em> $ <em> Curl foobar
....
```

[the reference documentation] Weitere Informationen finden Sie unter (https://github.com/gjtorikian/extended-markdown-filter#command-line-highlighting).

## Deploy

[Publisher] Deployments passieren automatisch, sobald ein PR in `master` verschmolzen wird. Ein Werkzeug, genannt (https://github.com/gjtorikian/publisher) führt den `master` Zweig, baut es Nanoc mit und veröffentlicht den Inhalt zu` gh-pages`. So verpflichten jede zu `master` wird automatisch auf` gh-pages` geschickt, wo sie abgeholt und serviert von GitHub Seiten.

## Lizenzen

Der Code zu erzeugen, um den Standort (alles mit Ausnahme der Vermögenswerte, Inhalt,
Und Layouts Verzeichnisse) sowie die Code-Beispiele auf der Website sind
Lizenziert unter
[CC0-1.0] (Https://creativecommons.org/publicdomain/zero/1.0/legalcode).
CC0 verzichtet auf alle Einschränkungen Urheberrecht aber nicht gewähren Sie eine Marke
Berechtigungen.

Website-Content (alles in den Vermögenswerten, Inhalte und Layouts Verzeichnisse,
Ausschließen von Dateien unter Open-Source-Lizenzen einzeln markiert) ist lizenziert
[CC-BY-4.0] unter (https://creativecommons.org/licenses/by/4.0/). CC-BY-4.0
Gibt Ihnen die Erlaubnis Inhalte für fast jeden Zweck zu verwenden, aber nicht gewährt
Sie irgendwelche Warenzeichen Berechtigungen, so lange, wie Sie die Lizenz beachten und Kredit geben,
Wie folgt:

> Content basierend auf
<a href="https://github.com/github/developer.github.com"> > </a> developer.github.com
> Unter den verwendeten
<a href="https://creativecommons.org/licenses/by/4.0/"> > </a> CC-BY-4.0
</a> > Lizenz.

Dies bedeutet, dass Sie den Code und Inhalt in diesem Repository verwenden können, mit Ausnahme von
GitHub Marken in Ihren eigenen Projekten.

Wenn tragen Sie zu diesem Repository Sie so unter den oben tun
Lizenzen.
cdomain/zero/1.0/legalcode).
CC0 verzichtet auf alle Einschränkungen Urheberrecht aber nicht gewähren Sie eine Marke
Berechtigungen.

Website-Content (alles in den Vermögenswerten, Inhalte und Layouts Verzeichnisse,
Ausschließen von Dateien unter Open-Source-Lizenzen einzeln markiert) ist lizenziert
[CC-BY-4.0] unter (https://creativecommons.org/licenses/by/4.0/). CC-BY-4.0
Gibt Ihnen die Erlaubnis Inhalte für fast jeden Zweck zu verwenden, aber nicht gewährt
Sie irgendwelche Warenzeichen Berechtigungen, so lange, wie Sie die Lizenz beachten und Kredit geben,
Wie folgt:

> Content basierend auf
<a href="https://github.com/github/developer.github.com"> > </a> developer.github.com
> Unter den verwendeten
<a href="https://creativecommons.org/licenses/by/4.0/"> > </a> CC-