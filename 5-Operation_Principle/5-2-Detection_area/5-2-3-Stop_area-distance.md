### 5.2.3	정지 영역 거리
영역1은 정지 영역에 해당하며, 레이더 센서가 활성화되면 영역1도 자동으로 활성화된다. TP에서 입력한 영역1 값은 시작 지점을 의미하며, 영역1의 종료 지점은 활성화된 다음 영역의 시작 지점에 따라 결정된다. 만약 활성화된 영역이 없다면, 사용자가 입력한 종료 지점 값이 영역1의 종료 지점으로 적용된다. 영역1의 시작 지점을 500으로 입력했을 때 영역1의 범위 예시는 아래와 같다.

<table>
  <thead>
    <tr>
      <th style="text-align: center;">예시</th>
      <th style="text-align: center;">파라미터</th>
      <th style="text-align: center;">활성화 상태</th>
      <th style="text-align: center;">입력값</th>
      <th style="text-align: center;">영역2 범위</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">1</td>
      <td>영역2</td>
      <td>활성화</td>
      <td>2000</td>
      <td>500 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="text-align: center; vertical-align: middle;">2</td>
      <td>영역2</td>
      <td>비활성화</td>
      <td>-</td>
      <td rowspan="2" style="text-align: center; vertical-align: middle;">500 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>영역3</td>
      <td>활성화</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="4" style="text-align: center; vertical-align: middle;">3</td>
      <td>영역2</td>
      <td>비활성화</td>
      <td>-</td>
      <td rowspan="4" style="text-align: center; vertical-align: middle;">500 ~ 4000 mm</td>
    </tr>
    <tr>
      <td>영역3</td>
      <td>비활성화</td>
      <td>-</td>
    </tr>
    <tr>
      <td>영역4</td>
      <td>비활성화</td>
      <td>-</td>
    </tr>
    <tr>
      <td>종료 지점</td>
      <td>-</td>
      <td>4000</td>
    </tr>
  </tbody>
</table>
