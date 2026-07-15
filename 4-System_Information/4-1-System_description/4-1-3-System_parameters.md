### 4.1.3	시스템 매개변수
시스템의 매개변수는 TP를 사용하여 수정할 수 있다. 사용자가 모니터링 가능한 매개변수의 구성과 기본 값은 다음과 같다.

<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">레이더 센서 설정</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">매개변수</td>
      <td style="text-align: center;">최소값</td>
      <td style="text-align: center;">최대값</td>
      <td style="text-align: center;">기본값</td>
      <td style="text-align: center;">비고</td>
    </tr>
    <tr>
      <td>활성화</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0 = 비활성화, 1 = 활성화</td>
    </tr>
    <tr>
      <td>영역1</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>레이더 센서 활성화 시 영역1 자동 활성화</td>
    </tr>
    <tr>
      <td>영역2</td>
      <td>500</td>
      <td>5000</td>
      <td>2000</td>
      <td>단위: mm</td>
    </tr>
    <tr>
      <td>영역3</td>
      <td>500</td>
      <td>5000</td>
      <td>3000</td>
      <td>단위: mm</td>
    </tr>
    <tr>
      <td>영역4</td>
      <td>500</td>
      <td>5000</td>
      <td>4000</td>
      <td>단위: mm</td>
    </tr>
    <tr>
      <td>종료 지점</td>
      <td>500</td>
      <td>5000</td>
      <td>5000</td>
      <td>단위: mm</td>
    </tr>
    <tr>
      <td>시작 방위각</td>
      <td>-55</td>
      <td>55</td>
      <td>-55</td>
      <td>단위: &deg</td>
    </tr>
    <tr>
      <td>종료 방위각</td>
      <td>-55</td>
      <td>55</td>
      <td>55</td>
      <td>단위: &deg</td>
    </tr>
  </tbody>
</table>
<br>

<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">레이더 객체 감지 파라미터</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">매개변수</td>
      <td style="text-align: center;">최소값</td>
      <td style="text-align: center;">최대값</td>
      <td style="text-align: center;">기본값</td>
      <td style="text-align: center;">비고</td>
    </tr>
    <tr>
      <td>인접거리</td>
      <td>1</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
    <tr>
      <td>최소 포인트 수</td>
      <td>1</td>
      <td>10</td>
      <td>4</td>
      <td></td>
    </tr>
    <tr>
      <td>최대 속도</td>
      <td>0</td>
      <td>140</td>
      <td>140</td>
      <td></td>
    </tr>
    <tr>
      <td>최소 연속 프레임 수</td>
      <td>1</td>
      <td>50</td>
      <td>1</td>
      <td></td>
    </tr>
    <tr>
      <td>최대 프레임 수</td>
      <td>1</td>
      <td>50</td>
      <td>30</td>
      <td></td>
    </tr>
    <tr>
      <td>최소 이동 거리</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td></td>
    </tr>
    <tr>
      <td>최대 반경</td>
      <td>0</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
  </tbody>
</table>
<br>

{% hint style="danger" %}
시스템 매개변수는 감지 성능에 직접적인 영향을 미치므로, 파라미터 설정 후 반드시 정상 작동 여부 및 위험성 평가 등을 수행해야 한다. 
{% endhint %}
