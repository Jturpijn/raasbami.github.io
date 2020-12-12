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
<!-- =================

Table styling
================= -->
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>

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
        <th> Ranking </th>
        <th> Points </th>
      </tr>
  {% for image in site.static_files reversed %}
      {% if image.path contains 'images/result' %}
      <tr>
        <td rowspan="3"  style="vertical-align:top"><img src="{{ image.path }}" alt="image" width="480" height="270" /> </td> 
          {% for race in site.data.races %}
          {% assign currRace = site.data.races | where: "id", image.basename  %} 
          {% endfor %}  
              <td> {{ currRace[0].date }} </td>
              <td> {{ currRace[0].first }} </td>
              <td> {{ currRace[0].first_points }} </td>
            </tr>
            <tr>
              <th>  # races </th>
              <td> {{ currRace[0].second }} </td>
              <td> {{ currRace[0].second_points }} </td>
            </tr>
            <tr>
              <td> {{ currRace[0].amount }} </td>
              <td> {{ currRace[0].third }} </td>
              <td> {{ currRace[0].third_points }} </td>
            </tr>
            <tr > <!-- Table spacer --> 
                <td colspan="4"></td> 
            </tr>
      {% endif %}
  {% endfor %}
</table>