### 5.2.4	경고 영역 거리
영역2 ~ 영역4는 경고 영역에 해당된다. TP에서 입력한 영역2 ~ 영역4 값은 각 영역의 시작 지점을 의미하며, 활성화된 다음 영역의 시작 지점은 이전 영역의 종료 지점이다. 영역2가 활성화되고 시작 지점이 1000mm로 설정되었을 때, 영역2의 범위는 아래와 같다.

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
      <td>영역3</td>
      <td>활성화</td>
      <td>2000</td>
      <td>1000 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="text-align: center; vertical-align: middle;">2</td>
      <td>영역3</td>
      <td>비활성화</td>
      <td>-</td>
      <td rowspan="2" style="text-align: center; vertical-align: middle;">1000 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>영역4</td>
      <td>활성화</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="3" style="text-align: center; vertical-align: middle;">3</td>
      <td>영역3</td>
      <td>비활성화</td>
      <td>-</td>
      <td rowspan="3" style="text-align: center; vertical-align: middle;">1000 ~ 4000 mm</td>
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
