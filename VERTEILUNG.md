# Verteilung, Schritt für Schritt

Reihenfolge nach Wirkung. Die offizielle Registry zuerst, weil mehrere
andere Verzeichnisse von dort automatisch nachziehen.

## 1. Offizielle MCP Registry

Kein Review, kostenlos, in Sekunden live. Glama und PulseMCP holen sich
den Eintrag danach von selbst.

Schlüsselpaar erzeugen:

    openssl genpkey -algorithm Ed25519 -out key.pem
    openssl pkey -in key.pem -pubout -outform DER | tail -c 32 | base64

Den ausgegebenen Wert einsetzen und auf systra.tools unter
/.well-known/mcp-registry-auth als reinen Text ausliefern:

    v=MCPv1; k=ed25519; p=DEIN_PUBLIC_KEY

Dann veröffentlichen:

    brew install mcp-publisher
    mcp-publisher validate
    mcp-publisher login http --domain systra.tools --private-key "$PRIVATE_KEY"
    mcp-publisher publish

Der private Schlüssel gehört nicht ins Repo. key.pem steht in .gitignore.

## 2. Glama Connectors

https://glama.ai/mcp/connectors

Name: Systra Tools
Server-URL: https://systra.tools/api/mcp
Transport: streamable-http
Beschreibung: siehe unten

Glama bewertet öffentlich sichtbar die Qualität der Tool-Beschreibungen.
Vorher einmal über die 13 Beschreibungen im MCP-Endpoint gehen.

## 3. Claude Plugin Directory

https://platform.claude.com/plugins/submit

Vorher lokal pruefen:

    claude plugin validate .

Wichtig: das offizielle Verzeichnis von Anthropic ist kuratiert und nimmt
keine Bewerbungen an. Das Formular fuehrt ins Community-Verzeichnis, das
ist der richtige Weg.

## 4. mcpservers.org

https://mcpservers.org/submit

Server Name: Systra Tools
Category: Design
Short Description: Gives coding agents 500+ production-ready React and
Tailwind sections to build from instead of writing UI from scratch.
URL: https://systra.tools
Contact Email: die Adresse eintragen, die ihr fuer das Produkt nutzt

## 5. mcp.so

https://mcp.so/submit?type=server, Typ "Remote Server"

Name: Systra Tools
Repository URL: https://github.com/roesmannamelie-alt/systra-tools-plugin

## 6. Docker MCP Registry

Fork von docker/mcp-registry, dann:

    task remote-wizard

Erzeugt server.yaml, tools.json (bei Remote leer) und readme.md.
Danach Pull Request. Nach Freigabe 24 Stunden bis live.

## 7. Cursor First-Party

https://cursor.com/marketplace/publish, Repo-Link einreichen.
Kuratiert, manuelle Pruefung auch bei jedem Update. Rechnet mit Wartezeit.

## Bewusst nicht eingereicht

PulseMCP: Einreichungen sind seit dem 03.09.2026 pausiert. Sie holen den
Eintrag automatisch aus der offiziellen Registry, sobald sie wieder oeffnen.

Smithery: verlangt fuer authentifizierte Server OAuth. Ohne OAuth ginge es
nur ueber ein Config-Schema mit x-from und x-to. Erst sinnvoll, wenn
jemand danach fragt.

aniftyco/awesome-tailwindcss: nimmt seit 2026 keine kostenpflichtigen
Produkte mehr auf, auch keine Free-Tiers davon. Ausserdem lehnt die Liste
von KI verfasste Pull Requests ausdruecklich ab. Faellt weg.

## Textbausteine

Kurzbeschreibung, 76 Zeichen, passt in das 100-Zeichen-Limit der Registry:

    Search and pull 500+ production-ready React + Tailwind sections and elements

Laengere Beschreibung fuer Verzeichnisse ohne Limit:

    Systra Tools is an MCP server that gives Cursor and Claude Code a real
    component library to build from: 500+ production-ready React + Tailwind
    sections and elements across 37 categories, plus 18 full page recipes
    and a style extractor that returns any component in a real brand's
    colours and fonts. Your agent searches, pulls the source, and pastes it.
