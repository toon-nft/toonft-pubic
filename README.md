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

### 1. 드롭다운

<p>
  <img src="https://user-images.githubusercontent.com/20431369/165225996-7d032813-1575-49ac-981d-21742d63500a.png">
</p>

```
# HTML
<div class="dropdown">
	<button
		class="dropdownToggle"
		type="button"
		data-toggle="dropdown"
	>
		<span>Recently Listed</span>
		<svg
			width="24"
			height="24"
			viewBox="0 0 24 24"
			class="arrow"
		>
			<path
				d="m7 10 5 5 5-5"
				stroke="#000"
				stroke-width="1.5"
				fill="none"
				fill-rule="evenodd"
				stroke-linecap="round"
				stroke-linejoin="round"
			/>
		</svg>
	</button>
	<div class="dropdown-menu">
		<button class="dropdown-item" type="button">
			Recently Listed
		</button>
		<button class="dropdown-item" type="button">
			Recently Created
		</button>
		<button class="dropdown-item" type="button">
			Recently Sold
		</button>
	</div>
</div>

# SCSS
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

### 2. 버튼

<p>
<img src="https://user-images.githubusercontent.com/20431369/165692350-dae11db6-5553-451d-a733-c77d1900f422.png">
</p>

버튼 사이즈 높이에 따라 `sm`,`md`,`lg`,`xl`,`xxl` 로 구분

```
# HTML
<button type="button" class="btnPrimary btn-xxl">
  Buy Now
</button>
<button type="button" class="btnOutlinePrimary btn-sm">
  Make offer
</button>

# SCSS

.btnOutlinePrimary {
  width: 100%;
  border-radius: 10px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  background-color: #fff;
  transition: all 0.2s ease;

  &.active {
    background-color: #000;
    border-color: #000;
    color: #fff;
  }

  &:hover:not(:disabled),
  &:focus:not(:disabled) {
    border-color: rgba(0, 0, 0, 0.9);
  }

  &:disabled {
    background-color: #e9ecef;
    border-color: rgba(0, 0, 0, 0.2);
    cursor: not-allowed;
  }
}

.btnPrimary {
  width: 100%;
  border-radius: 10px;
  border: 1px solid #000;
  background-color: #000;
  transition: all 0.2s ease;
  color: #fff;

  &.active {
    background-color: #ee312f;
    border-color: #ee312f;
    color: #fff;
  }
  &.active:hover:not(:disabled),
  &.active:focus:not(:disabled) {
    background-color: #ee312f;
    border-color: #ee312f;
    color: #fff;
  }

  &:hover:not(:disabled),
  &:focus:not(:disabled) {
    border: 1px solid lighten(#000, 15%);
    background-color: lighten(#000, 15%);
  }

  &:disabled {
    background-color: #e9ecef;
    border-color: rgba(0, 0, 0, 0.1);
    color: rgba(0, 0, 0, 0.15);
    cursor: not-allowed;
  }
}

```

### 3. 인풋:라디오

<p>
<img src="https://user-images.githubusercontent.com/20431369/167344061-c3af3411-813b-4bcd-bb67-055b69b7ad99.png">
</p>

```
#HTML
<label className="radio">
  <input type="radio" />
  <span className="radioLabel">Buying NFTs</span>
</label>
<label className="radio">
  <input type="radio" />
  <span className="radioLabel">Selling NFTs</span>
</label>
<label className="radio">
  <input type="radio" />
  <span className="radioLabel">Account / Login issues</span>
</label>
<label className="radio">
  <input type="radio" />
  <span className="radioLabel">Wallet and Transaction Errors</span>
</label>
<label className="radio">
  <input type="radio" />
  <span className="radioLabel">Other Issues</span>
</label>

#SCSS
.radio {
  display: inline-block;
  input[type="radio"] {
    @include sr-only();
  }

  .radioLabel {
    position: relative;
    display: inline-block;
    padding-left: 34px;
    cursor: pointer;
    font-size: 16px;

    &::before {
      content: "";
      position: absolute;
      left: 0;
      top: -3px;
      width: 24px;
      height: 24px;
      text-align: center;
      background: #fff;
      border: solid 1px rgba(0, 0, 0, 0.2);
      border-radius: 100%;
    }

    &::after {
      content: "";
      position: absolute;
      top: 4px;
      left: 7px;
      width: 10px;
      height: 10px;
      background-color: rgba(0, 0, 0, 0.05);
      border-radius: 100%;
    }
  }

  input[type="radio"]:checked + .radioLabel {
    &::before {
      border: 2px solid #ee312f;
    }
    &::after {
      background: #ee312f;
    }
  }
}
.radio:not(.d-block) + .radio:not(.d-block) {
  margin-left: 20px;
}
```

### 4. 로딩

<p>
<img src="https://user-images.githubusercontent.com/20431369/169003083-f015d18f-4245-4f55-989b-250d4e029ba0.png">
</p>

```
#HTML
<div class="followStep__progress followStep__progress--loading">
  <svg
    width="24"
    height="24"
    viewBox="0 0 24 24"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M5 12.5 9.667 17 19 8"
      stroke="#000"
      stroke-width="1.5"
      fill="none"
      fill-rule="evenodd"
      opacity=".2"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
  </svg>
</div>

#SCSS
.followStep {
  &__progress--loading {
    svg {
      display: none;
    }
  }
  &__progress--loading::after {
    content: "";
    display: block;
    position: absolute;
    top: -3px;
    left: -3px;
    z-index: 1;
    width: 34px;
    height: 34px;
    border: 3px solid transparent;
    border-left-color: #ee312f;
    border-radius: 50%;
    animation-name: loadingRotate;
    animation-duration: 1.2s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }
}

@keyframes loadingRotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

```
