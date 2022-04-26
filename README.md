# Toonft's technicals.

<p align="middle">
	<img src="https://user-images.githubusercontent.com/20431369/164615424-f3becc45-124e-47ca-a9db-9b28b9772608.png">
</p>

---

# 🎨 Toonft Template

`Gulp v3.9.1` 과 `Bootstrap v4.6.1` 로 구축된 마켓플레이스 템플릿입니다.
현재 디자인 템플릿은 초기버전이며 추후 `React 18`을 기반으로 변경될수 있습니다.

## 특징

다음과 같은 기능이 포함되어 있습니다.

- Gulp v3.9.1
- Gulp autoprefixer v5.0
- Gulp spritesmit multi v3.1.0
- Gulp file include v2.0.1
- Bootstrap V4.6.1
- Browser Sync v2.26
- Node sass v4.14

## Prettier

코드 포멧터 설정(.prettierrc)은 다음과 같습니다.

```
{
  "editor.formatOnSave": true,
  "prettier.semi": false,
  "prettier.javascriptEnable": ["javascript", "javascriptreact"],
  "prettier.printWidth": 200,
  "prettier.useTabs": false,
  "prettier.tabWidth": 2,
  "prettier.bracketSameLine": true
}
```

## 디자인 컴포넌트

### 1. DROPDOWN

<p align="middle">
  <img src="https://user-images.githubusercontent.com/20431369/165225996-7d032813-1575-49ac-981d-21742d63500a.png">
</p>

```
.dropdownToggle {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-width: 200px;
  padding: 0 10px;
  height: 40px;
  border-radius: 10px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  background: #fff;
  font-size: 16px;
}
.dropdown-menu {
  min-width: 200px;
  overflow: hidden;
  padding: 0;
  border-radius: 10px;
  border-color: rgba(0, 0, 0, 0.9);
}
.dropdown-item {
  height: 40px;
  line-height: 40px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  font-size: 16px;

  &:hover,
  &:focus {
    background-color: rgba(0, 0, 0, 0.7);
    color: #fff;
  }

  &:last-of-type {
    border-bottom: 0;
  }
}

.dropdown.show {
  .dropdownToggle {
    border-color: rgba(0, 0, 0, 0.9);
  }
  .arrow {
    transform: rotate(180deg);
  }
}
```
