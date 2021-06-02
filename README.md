Einleitung
----------

Diese vorwissenschaftliche Arbeit LaTeX-Vorlage wurde als Alternative zu der bereits vorhandenen Word-Vorlage von einem ehemaligen Schüler gemacht. Es ist zu beachten, dass die Angaben auf dem Titelblatt (Name des Schülers und des Betreuers, Jahrgang, Klasse, Titel und Untertitel) und in der eidesstattlichen Erklärung (Name des Schülers) geändert werden müssen. Im Restlichen ist dieses Dokument ausreichend kommentiert, weswegen das Benützen dieser Vorlage ziemlich selbsterklärend sein sollte. Zum Schluss werden in den nächsten Abschnitten ein paar Tipps bezüglich der Distribution und der restlichen technischen Sachen gegeben, die das Arbeiten mit dieser Vorlage vereinfachen sollten.

LaTeX-Distribution
------------------

Falls du noch keine bevorzugte Distribution hast, die du für deine vorwissenschaftliche Arbeit verwenden willst, will ich dir [TinyTeX](https://yihui.org/tinytex/) dringlich empfehlen. TinyTex ist eine von TexLive abgeleitet Distribution, die auf einer Vielzahl von Betriebssystemen läuft und leicht zu installieren beziehungsweise zu betätigen ist. Allerdings, da diese Distribution so schlicht und klein ist, werden nach der Installation vermutlich einige Pakete fehlen, die für diese Vorlage notwendig sind. Diese können jedoch ganz einfach mit dem mitgelieferten LaTeX-Paketmanager tlmgr installiert werden:

    TODO add packages

    tlmgr update --self
    tlmgr install

LaTeX-Compiler
--------------

LuaLatex ist ein LaTeX-Compiler, der sowohl in TexLive als auch TinyTex dabei ist und im Gegensatz zu den anderen, von mir ausprobierten, Compilern gleich *nach dem Auspacken* funktioniert. Unter anderem unterstützt dieser Compiler TrueType beziehungsweise OpenType Schriften und kann mit UTF-8 Dokumenten arbeiten, ohne dass zusätzliche Pakete benötigt werden. Ein LaTeX-Dokument kann auf folgende Art und Weise mit LuaLatex kompiliert werden:

    lualatex --output-directory=output document
    biber --output-directory=output --input-directory=output document
    lualatex --output-directory=output document
    lualatex --output-directory=output document

Es ist beachtenswert, dass der *output* Ordner, wenn er nicht bereits vorhanden ist, nicht von LaTeX erstellt wird und deswegen manuell angelegt werden muss. Schließlich wird die resultierende PDF-Datei als *output/document.pdf* ersichtlich sein. Natürlich macht es wenig Sinn, die Befehle jedes Mal von Grund auf neu einzugeben, weshalb sie in einem Skript gespeichert werden sollten.

Nützliche Hinweise
------------------

1. [LaTeX kann eine .sty Datei nicht finden](https://yihui.org/tinytex/#maintenance)

2. [How to Write a Thesis in LaTeX](https://www.overleaf.com/learn/latex/How_to_Write_a_Thesis_in_LaTeX_(Part_1):_Basic_Structure)

Andrey Proskurin (02.06.2021)
