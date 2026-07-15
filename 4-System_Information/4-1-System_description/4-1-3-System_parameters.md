### 4.1.3	System parameters
System parameters can be modified using the TP. Below are the configurations and default values of the parameters that can be monitored by the user:


<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">Radar sensor setting</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">Parameter</td>
      <td style="text-align: center;">Min.</td>
      <td style="text-align: center;">Max.</td>
      <td style="text-align: center;">Default</td>
      <td style="text-align: center;">Note</td>
    </tr>
    <tr>
      <td>Active</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0 = disable, 1 = enable</td>
    </tr>
    <tr>
      <td>zone1</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>Automatically activates when radar sensor is enabled</td>
    </tr>
    <tr>
      <td>zone2</td>
      <td>500</td>
      <td>5000</td>
      <td>2000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>500</td>
      <td>5000</td>
      <td>3000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>500</td>
      <td>5000</td>
      <td>4000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>End point</td>
      <td>500</td>
      <td>5000</td>
      <td>5000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>Valid azimuth start</td>
      <td>-55</td>
      <td>55</td>
      <td>-55</td>
      <td>Unit: &deg</td>
    </tr>
    <tr>
      <td>Valid azimuth end</td>
      <td>-55</td>
      <td>55</td>
      <td>55</td>
      <td>Unit: &deg</td>
    </tr>
  </tbody>
</table>
<br>

<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">Object detection parameter setting</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">Parameter</td>
      <td style="text-align: center;">Min.</td>
      <td style="text-align: center;">Max.</td>
      <td style="text-align: center;">Default</td>
      <td style="text-align: center;">Note</td>
    </tr>
    <tr>
      <td>epsilon</td>
      <td>1</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
    <tr>
      <td>min point</td>
      <td>1</td>
      <td>10</td>
      <td>4</td>
      <td></td>
    </tr>
    <tr>
      <td>max speed</td>
      <td>0</td>
      <td>140</td>
      <td>140</td>
      <td></td>
    </tr>
    <tr>
      <td>hit active</td>
      <td>1</td>
      <td>50</td>
      <td>1</td>
      <td></td>
    </tr>
    <tr>
      <td>hit stop</td>
      <td>1</td>
      <td>50</td>
      <td>30</td>
      <td></td>
    </tr>
    <tr>
      <td>idis</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td></td>
    </tr>
    <tr>
      <td>tracker radius</td>
      <td>0</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
  </tbody>
</table>
<br>

{% hint style="danger" %}
System parameters directly impact detection performance. Therefore, after configuring parameters, it is essential to verify proper functionality and conduct a comprehensive risk assessment.
{% endhint %}
