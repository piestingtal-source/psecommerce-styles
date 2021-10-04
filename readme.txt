Eigene Designs für PSeCommerce erstellen
Es gibt zwei Methoden, um benutzerdefinierte Designs für PSeCommerce-Shops zu erstellen:

Basis-Themes:
Basis-Themes bestehen aus einer CSS-Datei und einem optionalen Bilderordner, der geladen wird
und auf Shop-Seiten angewendet wird. So erstellst Du ein Basis-Theme:
1. Erstelle eine CSS-Datei im Verzeichnis /wp-content/psecommerce-styles/ mit Deinen benutzerdefinierten CSS Styles. Es ist möglicherweise am einfachsten, unser default.css-Design zu kopieren und zu ändern. Standard CSS zum bearbeiten Downloaden
2. Stelle sicher, dass Du den benutzerdefinierten Themen-Header mit dem Namen Deines Themes oben in der CSS-Datei hinzufügst:

/*
PSeCommerce Style: CUSTOMNAME
*/
Wenn Du diesen Header einfügst, wird Dein benutzerdefiniertes Theme in der Shoptheme Auswahl-Liste angezeigt
Store Settings -> Präsentationsseite, damit sie ausgewählt werden kann.
3. Optional kannst Du auch ein Unterverzeichnis für Deine CSS-Bilder im Ordner /wp-content/psecommerce-styles/ erstellen
und verlinke Bilder darin mit relativen URLs wie „image-folder/my-image.jpg“.

Erweiterte Themen:
PSeCommerce verwendet benutzerdefinierte Beitragstypen, um seine Artikel anzuzeigen. Dies bedeutet, dass Du das gleiche WP-Theme-Template-System, mit dem Du vertraut bist verwenden kannst.
Wir bieten lediglich eine angepasste Teilmenge der Vorlagenfunktionen, damit Du Dich nicht um Post-Metas kümmern musst. Vorlagenfunktionen sind vollständig dokumentiert und befinden sich in der Datei /psecommerce/includes/common/template-functions.php.
>psecommerce-template-functions downloaden<
Z.B. So erstellest Du eine benutzerdefinierte Produktseite:
1. Erstelle eine Kopie der Vorlagendatei page.php in Deinem Themenverzeichnis und benenne sie in mp_product.php um
2. mp_product.php muss die mp_* -Funktionen anstelle von the_content() verwenden. Eine Liste der für Produkte relevanten Funktionen findest Du in der template-functions.php.
PSeCommerce durchsucht Deinen aktuellen Themenordner nach Vorlagendateien, die für das Speichern von Seiten spezifisch sind. Hier sind mögliche Dateinamen für Templatevorlagen in der Reihenfolge der Abfrage:

Einzelne Produktseite
mp_product-PRODUCTNAME.php
mp_product-PRODUCTID.php
mp_product.php
single-PRODUCT_POST_TYPE.php (Der Beitragstyp kann je nach den Einstellungen der Website „product“ oder „mp_product“ sein)
single.php
index.php

Shopseite
mp_store.php
page.php
index.php

Warenkorb/Kasse-Seite
mp_checkout.php
mp_cart.php
page.php
index.php

Bestellübersichtsseite
mp_orderstatus.php
page.php
index.php

Artikelarchivseite
mp_productlist.php
page.php
index.php

Artikelkategorie Seite
mp_category-CATEGORYSLUG.php
mp_category-CATEGORYID.php
mp_category.php
mp_taxonomy.php
taxonomy-product_category-CATEGORYSLUG.php
taxonomy-product_category.php
mp_productlist.php
taxonomy.php
page.php
index.php

Artkel-Tag-Listenseite
mp_tag-TAGSLUG.php
mp_tag-TAGID.php
mp_tag.php
mp_taxonomy.php
taxonomy-product_tag-TAGSLUG.php
taxonomy-product_tag.php
mp_productlist.php
taxonomy.php
page.php
index.php

Globale Einträge – Funktioniert nur auf der Hauptseite/im Blog
Artikelarchivseite
mp_global_products.php
mp_productlist.php
page.php
index.php

Artikelkategorielistenseite
mp_global_category-CATEGORYSLUG.php
mp_global_category.php
mp_global_category_list.php
taxonomy-product_category-CATEGORYSLUG.php
taxonomy-product_category.php
mp_productlist.php
taxonomy.php
page.php
index.php

Artikel-Tag-Listenseite
mp_global_tag-TAGSLUG.php
mp_global_tag.php
mp_global_tag_list.php
taxonomy-product_tag-TAGSLUG.php
taxonomy-product_tag.php
mp_productlist.php
taxonomy.php
page.php
index.php