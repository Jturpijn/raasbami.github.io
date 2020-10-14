# Welcome racers

Deze website houdt de officiele score bij van het Raasbami Mario Kart Wii toernooi. 
Om verwarring en ruzie te voorkomen, hieronder de regels :

``` 

* We spelen op de wii.  
* Alleen cups waar alle 3 de leden van deelnemen zijn legitiem.
* De cups kunnen enkel bestaan uit 16 of 32, de rest wordt niet opgenomen.
* Voor het huidige seizoen kan niet van controller worden gewisseld.
* De races worden hier bijgehouden voor volledige transparantie.

```

# De spelers

De boiis van Raasdorperweg, born and raised in Lijnden. Mario Kart legendes. 

<table>
  {% for row in site. data. players %}

    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}

  {% endfor %}
</table>
<br>

# Recent races season 1

<table>
  <tr>
    <th> First table </th>
    <th> Second table </th>
  </tr>
  <tr>
    <table>
      {% for row in site. data. races %}
        {% if forloop.first %}
          <tr>
            {% for pair in row %}
              <th>{{ pair[0] }}</th>
          </tr>
        {% endfor %}
      {% endif %}

      {% tablerow pair in row %}
        {{ pair[1] }}
        {% endtablerow %}
      {% endfor %}
    </table>
  </tr>
  <tr>
    <table>
    </table>
  </tr>
</table>