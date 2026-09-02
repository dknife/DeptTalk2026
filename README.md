# AI로 만드는 FBX 3D 웹서비스 — 강의 자료

캐릭터·애니메이션 FBX를 WebGL(Three.js)로 재생·제어하는 웹서비스를,
**AI를 활용해 단계적으로 구축·배포**하는 과정을 담은 교육 자료입니다.

## 구성

```
index.html                      ← 강의 프리젠테이션 (reveal.js 슬라이드) ★메인
examples/
  01-basic-scene.html           3D 기본 씬
  02-load-character.html         캐릭터 FBX 로드
  03-apply-animation.html        애니메이션 입히기
  04-full-controls.html          제어 UI 완성본
fbx/
  character.fbx                  캐릭터(메시+스켈레톤)
  walk_ani.fbx                   걷기 애니메이션
```

## 실행 방법

FBX 로딩은 보안상 로컬 서버가 필요합니다 (더블클릭 `file://` 은 막힘).

```powershell
# 이 폴더에서 (택1)
python -m http.server 8000
npx serve .
```

- **강의 슬라이드:** http://localhost:8000/index.html  (방향키로 넘김, ESC로 전체 보기)
- **실습 완성본:** http://localhost:8000/examples/04-full-controls.html

## 배포 (GitHub Pages)

이 폴더를 GitHub 저장소에 올린 뒤, **Settings → Pages → Deploy from a branch (main / root)** 로 공개합니다.
공개 주소 예시:

```
https://<아이디>.github.io/<저장소>/            (슬라이드)
https://<아이디>.github.io/<저장소>/examples/04-full-controls.html
```

> 자세한 절차와 AI 활용 프롬프트·검증법은 `index.html` 슬라이드 참고.
