# AI로 만드는 FBX 3D 웹서비스 — 강의 자료

캐릭터·애니메이션 FBX를 WebGL(Three.js)로 재생·제어하는 웹서비스를,
**AI를 활용해 단계적으로 구축·배포**하는 과정을 담은 교육 자료입니다.

## 🌐 라이브 (GitHub Pages)

- **강의 프리젠테이션:** https://dknife.github.io/DeptTalk2026/
- **실습 예제 목록:** https://dknife.github.io/DeptTalk2026/examples/
- **저장소:** https://github.com/dknife/DeptTalk2026

## 구성

```
index.html                      ← 강의 프리젠테이션 (reveal.js 슬라이드) ★메인
examples/
  index.html                    실습 예제 런처 (01~05 순서대로)
  01-basic-scene.html           3D 기본 씬
  02-load-character.html        캐릭터 FBX 로드
  03-apply-animation.html       애니메이션 입히기
  04-full-controls.html         제어 UI 완성
  05-file-loader.html           파일 불러오기(업로드/드롭) UI
fbx/
  character.fbx                 캐릭터 (원본)
  walk_ani.fbx                  걷기 애니메이션 (원본)
glb/
  character.glb                 GLB 변환본 (49MB → 29MB)
  walk_ani.glb                  GLB 변환본 (34MB → 29MB)
```

## 로컬 실행

FBX 로딩은 보안상 로컬 서버가 필요합니다 (더블클릭 `file://` 은 막힘).

```powershell
python -m http.server 8000      # 또는  npx serve .
# 슬라이드:  http://localhost:8000/index.html
# 실습목록:  http://localhost:8000/examples/
```

## 배포 방법 (요약)

```powershell
git add .
git commit -m "업데이트 내용"
git push          # push 하면 GitHub Pages가 자동 갱신
```

> GitHub·Pages 개념과 절차, AI 활용 프롬프트·검증법, FBX→GLB 변환 과정은
> 모두 `index.html` 프리젠테이션에 담겨 있습니다.

## 참고 — FBX → GLB 변환

이 강의에서는 `fbx2gltf`(npm) 로 변환했습니다.

```javascript
// npm i fbx2gltf  후 실행
const convert = require('fbx2gltf');
convert('fbx/character.fbx', 'glb/character.glb', ['--binary']).then(console.log);
```

FBX(웹에 무거움) → GLB(웹 표준·경량)로 바꾸면 로딩이 빨라집니다.
모캡 애니메이션을 더 줄이려면 `@gltf-transform/cli optimize --compress meshopt` 등을 적용하세요.
