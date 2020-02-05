# ICONOS TINYMCE
Crear un font desde el sitio icomoon.io

![icomoon generate](/icomoon.png)

Se requiere asignar un valor en el mapa de caracteres de cada uno de los símbolos que se pretende usar. Esta reasinación tiene como objetivo evitar que se solape el símbolo por uno ya existente en dicha posición del font

![icomoon generate](/icomoon_key.png)

Una vez creado el mapa de caracteres y descargado el archivo font se debe usar el font en conjunción con otro font para unificar los símbolos en un sólo font que para este caso es *font-family: 'tinymce';* adicionalmente se puede especificar un rango de símbolos o ciertos símbolos mediante la instrucción *unicode-range: U+f322-fae2;*. Cada browser interpreta de forma diferente el font aunque la mayoría interpreta el tipo woff, el resto usará ttf, eot o svg.

~~~CSS
@font-face {
    font-family: 'tinymce';
    src: url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/tinymce.eot');
    src: url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/tinymce.eot?#iefix') format('embedded-opentype'), url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/tinymce.woff') format('woff'), url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/tinymce.ttf') format('truetype'), url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/tinymce.svg#tinymce') format('svg');
    font-weight: normal;
    font-style: normal
}
@font-face {
    font-family: 'tinymce';
    src: url('++plone++static/components/tinymce-builded/js/tinymce/skins/lightgray/fonts/icomoon.woff') format('woff');
    unicode-range: U+f322-fae2;

    font-weight: normal;
    font-style: normal
}
~~~

Una vez integrado el font se puede acceder a los los símbolos YouTube, Music y PDF se accede con el mapeo acá especificado. De esta forma se integran los símbolos al font *font-family: 'tinymce';* para ser usados por plugins dentro del TinyMCE.

~~~CSS
.mce-i-youtube:before {
    content: "\f322"
}
.mce-i-music:before {
    content: "\f911"
}
.mce-i-pdf:before {
    content: "\fadf"
}
~~~

La ruta de los plugins para el plone se encuentra en la ruta
"eggs/Products.CMFPlone-5.1.6-py2.7.egg/Products/CMFPlone/static/components/tinymce-builded/js/tinymce/plugins/"


