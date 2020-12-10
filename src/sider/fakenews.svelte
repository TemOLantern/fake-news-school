<script>
import Header from "../template/header.svelte";
import Picture from "../template/picture.svelte";

  </script>
  <Header name={"Fake news"}/>
  <div>
      <Picture float={"right"} img={"https://www.bistandsaktuelt.no/globalassets/bilder/nyhets-og-illustrasjonsbilder/2020/oktober/trump-v-biden-12x9-ntb_inruemsqddm.jpg?preset=Fluid1199"}/>
        <p>Falske nyheter er antagelig den metoden som har fått mest oppmerksomhet, 
        særlig fordi president Trump på imponerende måte har greid å utvanne hele begrepet gjennom sin bruk av «fake news media» – 
        der «fake news» er det samme som kritikk av ham som person. Falske nyheter og post-truth er blitt et skjellsord som brukes om nyhetssaker man ikke liker.
        <br><br>
        </p>
        <Picture float={"right"} img={"https://citacoesdosampaio.files.wordpress.com/2016/05/mark-zuckerberg-facebook-empresc3a1rio-e-programador-7.png"}/>
        <p id="dump">
        Dette reflekteres også i norsk debatt. Bruk av falske nyheter er ikke noe nytt, bruk av propaganda i ulike former er like gammelt som 
    menneskeheten selv, men effekten av internett er dramatisk. De siste avsløringene tyder på at falske nyheter på Facebook nådde nesten 130 millioner velgere. 
    Like fullt er falske nyheter/propaganda mindre vanskelig å avsløre enn de andre metodene. I mange tilfeller vil et minimum av kritisk sans være det som trengs for å avsløre falske nyheter.
        </p>  
  </div>
    <style>
      #dump{
        margin-top: -10px;
      }
       p{
         margin: 10px;
        font-size: xx-large;
        margin-top: -25px;
        display: block;
        line-height: 1.5056;
    }

    </style>