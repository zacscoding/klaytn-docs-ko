# 스토리지 레이어(Storage Layer)

## 블록 아카이빙

Klaytn의 처리량이 높아지면 스토리지 비용이 높아집니다. Klaytn은 참여 노드의 스토리지 부담을 줄이기 위해 블록 아카이빙을 할 계획입니다. 블록 아카이빙이 이루어진 경우 EN(Endpoint Node)은 오래된 블록의 몸통(body) 부분을 제거하여 마지막 특정 개수의 블록만 유지할 수 있습니다. Klaytn 네트워크 노드의 하위 그룹만 모든 블록을 비용면에서 효율적인 스토리지에 보관하고, EN에 더 이상 저장되어 있지 않은 이전의 트랜잭션을 확인하여 읽기 요청을 처리합니다. 그러나, 블록 아카이빙을 하는 EN도 아카이브된 모든 블록의 헤더는 가질 것입니다. 클라이언트가 아카이브된 블록의 내용을 안전하게 검증하기 위해서입니다.

이 과정은 EN의 스토리지 비용을 효과적으로 줄여서, 다양한 참여자가 ENN에 참여하도록 도울 것입니다. 평균 TPS가 100개이고 블록 지연 시간이 1초라고 가정할 때 EN이 복제해야 하는 데이터의 크기는 상당히 클 수 있습니다. 만약 평균 트랜잭션의 크기가 300바이트인 경우 EN은 하루에 2.5 GB가 필요할 것입니다(=300*100*86400). 이는 서버 및 데스크톱(스토리지가 더 쉽게 확장되고 비용이 적게 드는 경우)을 노드로 사용할 때는 괜찮지만, 노트북과 같은 경량 시스템에서는 이러한 스토리지 요구 사항이 부담스러울 수 있습니다. EN이 오직 고정된 숫자의 블록만 유지하는 것을 허용함으로써 블록 아카이빙은 네트워크 참여자를 다양화하고, 끝없이 커지는 블록체인의 블록을 모두 복제하지 않고도 보안성과 데이터 다중화(redundancy)를 강화할 수 있습니다.

블록 아카이빙 노드는 다른 노드의 도움 없이는 과거의 모든 트랜잭션을 독립적으로 확인할 수 없기 때문에 블록의 몸통(body)를 제거하는 것은 탈중앙화를 약화시키는 것으로 인식될 수도 있습니다. 그럼에도 모든 어플리케이션이 트랜잭션의 전체 기록에 지속적으로 액세스할 필요는 없습니다. 블록 아카이빙은 최신 어플리케이션 상태만 필요한 서비스 그룹은 선호하고 환영할 만한 기능이라고 생각합니다. 이러한 맥락에서 모든 블록을 모든 노드가 저장하는 것은 비효율적이며 바람직하지 않습니다. 블록 아카이빙은 높은 복제 수준과 보안을 필요로 하는 많은 어플리케이션에 도움이 될 것이라 믿습니다.