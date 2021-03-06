# Toonft's technicals.

<p align="middle">
	<img src="https://user-images.githubusercontent.com/20431369/164615424-f3becc45-124e-47ca-a9db-9b28b9772608.png">
</p>

---

# π¨ Toonft Template

`Gulp v3.9.1` κ³Ό `Bootstrap v4.6.1` λ‘ κ΅¬μΆλ λ§μΌνλ μ΄μ€ ννλ¦Ώμλλ€.
νμ¬ λμμΈ ννλ¦Ώμ μ΄κΈ°λ²μ μ΄λ©° μΆν `React 18`μ κΈ°λ°μΌλ‘ λ³κ²½λ μ μμ΅λλ€.

## νΉμ§

λ€μκ³Ό κ°μ κΈ°λ₯μ΄ ν¬ν¨λμ΄ μμ΅λλ€.

- Gulp v3.9.1
- Gulp autoprefixer v5.0
- Gulp spritesmit multi v3.1.0
- Gulp file include v2.0.1
- Bootstrap V4.6.1
- Browser Sync v2.26
- Node sass v4.14

## Prettier

μ½λ ν¬λ©§ν° μ€μ (.prettierrc)μ λ€μκ³Ό κ°μ΅λλ€.

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

## λμμΈ μ»΄ν¬λνΈ

### 1. λλ‘­λ€μ΄

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

### 2. λ²νΌ

<p>
<img src="https://user-images.githubusercontent.com/20431369/165692350-dae11db6-5553-451d-a733-c77d1900f422.png">
</p>

λ²νΌ μ¬μ΄μ¦ λμ΄μ λ°λΌ `sm`,`md`,`lg`,`xl`,`xxl` λ‘ κ΅¬λΆ

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

### 3. μΈν:λΌλμ€

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

### 4. λ‘λ©

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
