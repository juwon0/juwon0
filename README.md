# 임주원 (Juwon Lim)

## Open source contributions

**[stuartcrobinson/unique-window-colors](https://github.com/stuartcrobinson/unique-window-colors)** — VS Code 확장

- [#74](https://github.com/stuartcrobinson/unique-window-colors/issues/74) — VS Code 1.131 모던 UI 가 타이틀바·액티비티바·상태바 색상 커스터마이징을 무시하는 문제 원인 규명. 확장 버그가 아니라 업스트림 회귀임을 밝히고, `workbench.experimental.modernUI` 가 선언상 기본값 `false` 인데도 실험 `mode: "auto"` 로 켜져서 진단이 어려웠던 지점까지 정리. README 안내 반영됨 (v1.2.11). 업스트림 [microsoft/vscode#326126](https://github.com/microsoft/vscode/issues/326126) 은 [PR #329701](https://github.com/microsoft/vscode/pull/329701) 로 수정되어 1.133.0 에 릴리스
- [#75](https://github.com/stuartcrobinson/unique-window-colors/issues/75) — `.vscode/settings.json` 은 JSONC 인데 `JSON.parse` 로 읽어 창 종료 시 `SettingsFileDeleter.dispose` 가 예외를 던지던 버그 리포트. `jsonc-parser` 도입으로 수정됨 (master, v1.2.11)
