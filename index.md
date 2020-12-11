---
layout: default
title: Homepage
---
# Da Rules
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
  {% for player in site.data.players %}
    {% if forloop.first %}
      <tr>
        {% for pair in player %}
          <th>{{ pair[0]}}</th>
        {% endfor %}
      </tr>
    {% endif %}
    <tr>
      {% for pair in player %}
        <td>{{ pair[1]}}</td>
      {% endfor %}
    </tr>
  {% endfor %}
</table>
# Race History
<table>
      <tr>
        <th> Result </th>
        <th> Date </th>
        <th> Races </th>
        <th colspan="2"> 1st place </th>
        <th colspan="2"> 2nd place </th>
        <th colspan="2"> 3rd place </th>
      </tr>
  {% for image in site.static_files %}
      {% if image.path contains 'images/result' %}
      <tr>
        <td> <img src="{{ site.baseurl }}{{ image.path }}" colspan="3" alt="image" width="160" height="90" /> </td> 
          {% for race in site.data.races %}
          {% assign currRace = site.data.races | where: "ID", image.basename | first %} 
          {% endfor %}
              <td> {{ currRace."first" }} </td>
              <td> {{ currRace.last}} </td>
              <td> {{ currRace }} </td>
              <td> {{ currRace.Date }} </td>
              <td> {{ currRace.third }} </td>
      </tr>
      {% endif %}
  {% endfor %}
</table>