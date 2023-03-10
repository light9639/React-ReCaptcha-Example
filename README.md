# ๐๏ธ React์ react-google-recaptcha ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ด์ฉํ์ฌ ๋ง๋  ReCaptcha V2, V3 ๋ฌธ์์๋๋ค.
 
| <img src="https://user-images.githubusercontent.com/95972251/218261135-2bb1aea4-876d-4cf1-b6bd-0a86853b7e97.png" alt="Light" /> | <img src="https://user-images.githubusercontent.com/95972251/218261134-b1d6b8bf-7d76-467d-be4b-099eb836979f.png" alt="Dark" /> |
| ------------- | ------------- |

:sparkles: ๐๏ธ React์ react-google-recaptcha ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ด์ฉํ์ฌ ๋ง๋  ReCaptcha V2, V3 ๋ฌธ์์๋๋ค. :sparkles:
## :tada: React ํ๋ก์ ํธ ์์ฑ
- React ์์ฑ
```bash
npm create-react-app my-app
# or
yarn create react-app my-app
```

- vite๋ฅผ ์ด์ฉํ์ฌ ํ๋ก์ ํธ๋ฅผ ์์ฑํ๋ ค๋ฉด
```bash
npm create vite@latest
# or
yarn create vite
```
- ํฐ๋ฏธ๋์์ ์คํ ํ ํ๋ก์ ํธ ์ด๋ฆ ๋ง๋  ํ React ์ ํ, Typescirpt-SWC ์ ํํ๋ฉด ์์ฑ ์๋ฃ.
## ๐  'react-google-recaptcha-v3', 'react-google-recaptcha' ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ค์น
- `ReCaptcha`๋ฅผ ์ด์ฉํ์ฌ ์ฌ์ฉ์๊ฐ ์ฌ๋์ธ์ง ๋ก๋ด์ธ์ง๋ฅผ ์๊ณ  ์ถ๋ค๋ฉด `ReCaptcha`๋ฅผ React์์ ์ฝ๊ฒ ์ฌ์ฉํ  ์ ์๋๋ก ๋์์ฃผ๋ `react-google-recaptcha` ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ค์นํด์ ์งํํด์ผ ํ๋ค. ๊ทธ๋ผ, ์๋ ๋ช๋ น์ด๋ก ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ค์นํ๋ค.
```bash
$ npm install react-google-recaptcha-v3 react-google-recaptcha
# or
$ yarn add react-google-recaptcha-v3 react-google-recaptcha
```
## โ๏ธ .env ํ์ผ ์ธํ
### โก .env
- `.env` ํ์ผ์๋ `ReCaptcha` ์ฌ์ดํธ์์ ๋ฐ๊ธ๋ฐ์ 2๊ฐ์ง `key`๊ฐ์ ๋ฃ์ด์ผ ํ๋ค.
- ์ด์ ๋ํ ์ธ๋ถ ์ฌํญ์ <a href="https://whwp0913.me/%EA%B5%AC%EA%B8%80-reCAPTCHA-v3-%EB%B0%9C%EA%B8%89-%EB%B0%8F-%EC%A0%81%EC%9A%A9">๋งํฌ</a>๋ฅผ ์ฐธ์กฐํ๊ธฐ ๋ฐ๋๋ค.
```bash
VITE_V2_KEY={ReCaptcha 2๋ฒ์ ์ key ๊ฐ}
VITE_V3_KEY={ReCaptcha 3๋ฒ์ ์ key ๊ฐ}
```
## โ๏ธ App.tsx ์์  ๋ฐ ์์ฑ
### โก App.tsx
- `Captcha2.tsx`, `Captcha3.tsx`๋ฅผ `import`ํ์ฌ `div.card` ์์ ์์น์ํจ๋ค.
```typescript
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import ReCaptcha from './assets/ReCaptcha.png'
import './App.css'
import Captcha2 from '@components/Captcha2'
import Captcha3 from '@components/Captcha3'

export default function App(): JSX.Element {
  return (
    <div className="App">
      <div>
        <a href="https://www.npmjs.com/package/react-google-recaptcha" target="_blank">
          <img src={ReCaptcha} className="logo" alt="ReCaptcha" />
        </a>
        <a href="https://reactjs.org" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>React-ReCaptcha-Pages</h1>
      <div className="card">
        <Captcha2 />
        <Captcha3 />
      </div>
      <p className="read-the-docs">
        Click on the React and ReCaptcha logos to learn more
      </p>
    </div>
  )
}
```
## ๐ components ํ์ผ ์ Captcha2.tsx, Captcha3.tsx ์์  ๋ฐ ์์ฑ
### โก Captcha2.tsx
- `ReCaptcha`์ 2๋ฒ์ ผ ์ค ์ด๋ฏธ์ง ์ ํ ํ์์ ๊ณ ๋ฅธ ํ `import.meta.env.VITE_V2_KEY`๋ก `.env`์ key ๊ฐ์ ํตํด ์๋์ํจ๋ค.
```typescript
import React from "react";
import ReCAPTCHA from "react-google-recaptcha";

const Captcha2 = () => {
    const recaptchaRef = React.useRef() as React.MutableRefObject<HTMLFormElement>;

    const onSubmitWithReCAPTCHA = async () => {
        const token = await recaptchaRef.current.executeAsync();
    }

    return (
        <form onSubmit={onSubmitWithReCAPTCHA}>
            <ReCAPTCHA
                ref={recaptchaRef}
                sitekey={import.meta.env.VITE_V2_KEY}
            />
        </form>
    )

}

export default Captcha2
```
### โก Captcha3.tsx
- `ReCaptcha`์ 3๋ฒ์ ผ์ ์ฌ์ฉ์๊ฐ ์๋์ผ๋ก ์ฌ๋์ธ์ง ๊ธฐ๊ณ์ธ์ง๋ฅผ ํ๋จํด์ค๋ค.
- ์์์ ์์ฑํ ๋ด์ฉ๊ณผ ๋์ผํ๊ฒ `import.meta.env.VITE_V3_KEY`๋ `.env`์ key ๊ฐ์ ํตํด ์๋์ํฌ ์ ์๋ค.
```typescript
import React from "react";
import ReCAPTCHA from "react-google-recaptcha";

const Captcha3 = () => {
    const recaptchaRef = React.useRef() as React.MutableRefObject<HTMLFormElement>;

    const onSubmitWithReCAPTCHA = async () => {
        const token = await recaptchaRef.current.executeAsync();
    }

    return (
        <form onSubmit={onSubmitWithReCAPTCHA}>
            <ReCAPTCHA
                ref={recaptchaRef}
                size="invisible"
                sitekey={import.meta.env.VITE_V3_KEY}
            />
        </form>
    )

}

export default Captcha3
```
## ๐ ์ถ์ฒ
- <a href="https://velog.io/@rnrn99/reCAPTCHA-%EC%82%BD%EC%A7%88-%EA%B8%B0%EB%A1%9D">reCAPTCHA ์ฝ์ง ๊ธฐ๋ก</a>
- <a href="https://whwp0913.me/%EA%B5%AC%EA%B8%80-reCAPTCHA-v3-%EB%B0%9C%EA%B8%89-%EB%B0%8F-%EC%A0%81%EC%9A%A9">๊ตฌ๊ธ reCAPTCHA (v3) ๋ฐ๊ธ ๋ฐ ์ ์ฉ</a>
