# Welcome nerds.

Deze website houdt de officiele score bij van het Raasbami Mario Kart Wii toernooi.  
Om verwarring en ruzie te voorkomen, hieronder de regels :
```
- We spelen op de wii.  
- Alleen cups waar alle 3 de leden van deelnemen zijn legitiem.
- De cups kunnen enkel bestaan uit 16 of 32, de rest wordt niet opgenomen.
- Voor het huidige seizoen kan niet van controller worden gewisseld.
- De races worden hier bijgehouden voor volledige transparantie.
```

# De spelers
De bois van Raasdorperweg, born and raised in Lijnden. Mario Kart legendes.

<table>
  {% for row in site.data.players %}
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
  {% for row in site.data.races %}
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

# Total points per person
<ul>
{% for place in site.data.cups.races.places %}
{% if place.first_place == "joshua" %}
<li>{{place.first_place.points}}</li>
{% endif %}
{% endfor %}
</ul>