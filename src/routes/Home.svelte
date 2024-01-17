<!-- +++++ js +++++ -->
<script>
// @ts-nocheck

  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import { iso31661 } from 'iso-3166'

  const regionNamesInTraditionalChinese = new Intl.DisplayNames(['zh-Hant'], { type: 'region' });
  const regionNamesInJapan = new Intl.DisplayNames(['ja'], { type: 'region' });

  function getRandomNumber(min ,  max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }
  let setRandomNumber = getRandomNumber(1, 249); 
  let setRandomCountryCode = iso31661[setRandomNumber].alpha2;

  let chineseName;
  let changeHandler = (val) => {
    chineseName = regionNamesInTraditionalChinese.of(val);
  }
  
  let japanName;
  let answerHandler = (val) => {
    japanName = regionNamesInJapan.of(val);
  }
  
</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<Header/>
<main>
  <h1>How do you say this country in china???</h1>

  <p class="outputName" on:load={changeHandler(setRandomCountryCode)}>{chineseName}</p>
  <div class="outputAnswerWrap">
    <button class="outputAnswer" on:click={() => answerHandler(setRandomCountryCode)}>{japanName === undefined ? "答え" : japanName}</button>
  </div>
  <div class="nextButtonWrap">
    <button type="button" on:click={() => changeHandler(setRandomCountryCode)} class="nextButton">next</button>
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
    }

    /* .fadeDisplay {
      opacity: 0;
    } */
</style>
<!-- +++++ end +++++ -->