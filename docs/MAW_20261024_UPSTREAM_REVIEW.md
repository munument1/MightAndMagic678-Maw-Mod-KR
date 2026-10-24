# Maw Mod 신규 보스/전투 변경 이식 검토

공식 원본: https://github.com/Malekitsu/Maw-Mod-MMMerge

기존 확인 기준 `96b71303af2e73230591fbac7552f0868877016c`에서 최신 조회 HEAD `b10ded816188e8ebe1d943dda1c4521c034f8cc6`까지 공식 비교: 8개 커밋, 17개 변경 파일.

- 몬스터 특성·이름·능력 관련: `Scripts/General/zzMaw-Monsters.lua`, `Scripts/General/zzMaw_MonsterHit.lua`.
- 신규 공격속도 모듈: `Scripts/Modules/MawCore/MonsterAttackSpeed.lua`.
- 동기화/멀티플레이 변경: `Scripts/Modules/MawCore/Sync.lua`, `Scripts/Modules/Multiplayer/Hooks.lua` 및 동기화 모듈들.
- 주문·스킬 및 피해 처리: `Scripts/General/zzMaw-Spells.lua`, `Scripts/General/zzMAW-Skills.lua`, `Scripts/Modules/MawCore/Damage.lua`.

## 안전한 이식 순서

1. 기존 `korean-localization-4.5` 번역/오버레이 기준과 각 원본 변경 파일을 비교한다.
2. `Skilled` 같은 **내부 판정 문자열은 변경하지 않고**, 화면 표시만 별도 한국어 치환 경로로 분리한다.
3. 신규 보스 이름·설명, 스킬/주문 문구를 실제 문자열 출처에서 추출하고 번역한다.
4. 전투 속도와 멀티플레이 동기화 회귀 검증 후 패키징한다.

**현재 상태:** 변경 파일 식별 및 작업 계획 작성. 게임 코드 병합·번역 수정·실행 검증은 미완료.
