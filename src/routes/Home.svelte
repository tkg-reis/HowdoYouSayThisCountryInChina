<!-- +++++ js +++++ -->
<script>
// @ts-nocheck

  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import { iso31661 } from 'iso-3166'

  const regionNamesInTraditionalChinese = new Intl.DisplayNames(['zh-Hant'], { type: 'region' });
  const regionNamesInJapan = new Intl.DisplayNames(['ja'], { type: 'region' });
  const regionNamesInRussia = new Intl.DisplayNames(['RU'], { type: 'region' });
  const regionNamesInFinland = new Intl.DisplayNames(['FI'], { type: 'region' });

  function getRandomNumber(min ,  max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }
  // console.log(iso31661);
  let setRandomNumber = getRandomNumber(1, 249); 
  let setRandomCountryCode = iso31661[setRandomNumber].alpha2;

  let chineseName;
  let changeHandler = (val) => {
    chineseName = regionNamesInTraditionalChinese.of(val);
  }

  let russiaName;
  let changeHandler2 = (val) => {
    russiaName = regionNamesInRussia.of(val);
  }

  let finlandName;
  let changeHandler3 = (val) => {
    finlandName = regionNamesInFinland.of(val)
  }
  
  let japanName;
  let timeout = 3000;
  let answerHandler = (val) => {
    japanName = "";
    setTimeout(() => {
      japanName = regionNamesInJapan.of(val);
    }, timeout);
  }
  
  let nextHandler = () => {
    setRandomNumber = getRandomNumber(1, 250);
    setRandomCountryCode = iso31661[setRandomNumber].alpha2;
    changeHandler(setRandomCountryCode);
    changeHandler2(setRandomCountryCode);
    changeHandler3(setRandomCountryCode);
    answerHandler(setRandomCountryCode);
  }
</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<Header/>
<main>
  <h1>How do you say this country in .....</h1>

  <p class="outputName" on:load={changeHandler(setRandomCountryCode)}>{chineseName === undefined ? "問題" : `中国 : ${chineseName}`}</p>
  <p class="outputName" on:load={changeHandler2(setRandomCountryCode)}>{russiaName === undefined ? "は" : `露西亜 : ${russiaName}`}</p>
  <p class="outputName" on:load={changeHandler3(setRandomCountryCode)}>{finlandName === undefined ? "下を" : `芬蘭 : ${finlandName}`}</p>
  <div class="outputAnswerWrap">
    <button class="outputAnswer" on:click={() => answerHandler(setRandomCountryCode)}>{japanName === undefined ? "答え" : japanName}</button>
  </div>
  <div class="nextButtonWrap">
    <button type="button" on:click={() => nextHandler()} class="nextButton">{japanName === undefined ? "クリックで開始" : "next"}</button>
  </div>
</main>
<Footer/>
<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>
    .outputAnswerWrap {
      text-align: center;
    }
    .outputName {
      text-align: center;
      font-size: 24px;
      margin: 24px;
    }


    .nextButtonWrap {
      text-align: center;
    }
    
    .nextButton {
      padding: 8px 16px;

    }

    .outputAnswer {
      text-align: center;
      margin: 16px;
      border: none;
      background: #fafafa;
      box-shadow: 2px 2px 4px #333;
      font-size: 30px;
    }

    /* .fadeDisplay {
      opacity: 0;
    } */
</style>
<!-- +++++ end +++++ -->