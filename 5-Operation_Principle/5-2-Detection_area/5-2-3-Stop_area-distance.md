### 5.2.3	Stop area distance
Zone 1 corresponds to the stop zone; when the radar sensor is activated, Zone 1 is also automatically enabled. The Zone 1 value entered via the TP represents its starting point, whereas its ending point is determined by the starting point of the next active zone. If no other zones are active, the user-defined value is applied as the ending point. Below are examples of the Zone 1 range when the starting point is set to 500:

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
      <td>zone2</td>
      <td>enable</td>
      <td>2000</td>
      <td>500 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="vertical-align: middle;">2</td>
      <td>zone2</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="2" style="vertical-align: middle;">500 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>enable</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="4" style="vertical-align: middle;">3</td>
      <td>zone2</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="4" style="vertical-align: middle;">500 ~ 4000 mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
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
