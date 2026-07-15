### 5.2.4	Warning area distance
Zone2 ~ zone4 correspond to the warning zones. The values entered in the TP for these zones represent their respective starting points; the starting point of the next activated zone serves as the end point of the previous zone. For example, when zone2 is activated with its starting point set to 1000 mm, its range is defined as follows:

<table>
  <thead>
    <tr>
      <th style="text-align: center;">Ex.</th>
      <th style="text-align: center;">Parameter</th>
      <th style="text-align: center;">Activation status</th>
      <th style="text-align: center;">Input value</th>
      <th style="text-align: center;">Zone2 range</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>zone3</td>
      <td>enable</td>
      <td>2000</td>
      <td>1000 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="vertical-align: middle;">2</td>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="2" style="vertical-align: middle;">1000 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>enable</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="3" style="vertical-align: middle;">3</td>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="3" style="vertical-align: middle;">1000 ~ 4000 mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>disable</td>
      <td>-</td>
    </tr>
    <tr>
      <td>End point</td>
      <td>-</td>
      <td>4000</td>
    </tr>
  </tbody>
</table>
