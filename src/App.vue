<template>
  <div id="app">
    <h1><strong>Hacktools</strong> | Latallah</h1>
    <hr>

    <div class="container">
      <div class="row">
        <div class="col-sm-8">
          <b-form-group
            id="fieldset-horizontal"
            label-align="left"
            label-cols-sm="4"
            label-cols-lg="3"
            label="Wrestler ID"
            label-for="input-horizontal">
            <b-form-select :options="wrestlerId" v-model="wrestlerIdValue" :selected="wrestlerIdValue">
            </b-form-select>
          </b-form-group>

          <hr>
          <br>

          <div class="container">
            <div class="row">
              <div class="col-6">
                <b-form-group
                  id="mmmUpValue"
                  label-align="left"
                  label="B + Up"
                  label-for="input-horizontal">
                  <b-form-select :options="masterMoveMods" v-model="mmmUpValue" :selected="mmmUpValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="cpUpValue"
                  label-align="left"
                  label="Connection points"
                  label-size="sm">
                  <b-form-select :options="connectionPoints" v-model="cpUpValue" :selected="cpUpValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="sellUpValue"
                  label-align="left"
                  label="Sell animation"
                  label-size="sm">
                  <b-form-select :options="sellAnimations" v-model="sellUpValue" :selected="sellUpValue">
                  </b-form-select>
                </b-form-group>
              </div>
            </div>
            <div class="row">
            </div>
            <div class="row">
              <div class="col-6">
                <b-form-group
                  id="mmmLeftValue"
                  label-align="left"
                  label="B + Left"
                  label-for="input-horizontal">
                  <b-form-select :options="masterMoveMods" v-model="mmmLeftValue" :selected="mmmLeftValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="cpLeftValue"
                  label-align="left"
                  label="Connection points"
                  label-size="sm">
                  <b-form-select :options="connectionPoints" v-model="cpLeftValue" :selected="cpLeftValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="sellLeftValue"
                  label-align="left"
                  label="Sell animation"
                  label-size="sm">
                  <b-form-select :options="sellAnimations" v-model="sellLeftValue" :selected="sellLeftValue">
                  </b-form-select>
                </b-form-group>
              </div>
            </div>
            <div class="row">
            </div>
            <div class="row">
              <div class="col-6">
                <b-form-group
                  id="mmmRightValue"
                  label-align="left"
                  label="B + Right"
                  label-for="input-horizontal">
                  <b-form-select :options="masterMoveMods" v-model="mmmRightValue" :selected="mmmRightValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="cpRightValue"
                  label-align="left"
                  label="Connection points"
                  label-size="sm">
                  <b-form-select :options="connectionPoints" v-model="cpRightValue" :selected="cpRightValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="sellRightValue"
                  label-align="left"
                  label="Sell animation"
                  label-size="sm">
                  <b-form-select :options="sellAnimations" v-model="sellRightValue" :selected="sellRightValue">
                  </b-form-select>
                </b-form-group>
              </div>
            </div>
            <div class="row">
            </div>
            <div class="row">
              <div class="col-6">
                <b-form-group
                  id="mmmDownValue"
                  label-align="left"
                  label="B + Down"
                  label-for="input-horizontal">
                  <b-form-select :options="masterMoveMods" v-model="mmmDownValue" :selected="mmmDownValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="cpDownValue"
                  label-align="left"
                  label="Connection points"
                  label-size="sm">
                  <b-form-select :options="connectionPoints" v-model="cpDownValue" :selected="cpDownValue">
                  </b-form-select>
                </b-form-group>
              </div>
              <div class="col-3">
                <b-form-group
                  id="sellDownValue"
                  label-align="left"
                  label="Sell animation"
                  label-size="sm">
                  <b-form-select :options="sellAnimations" v-model="sellDownValue" :selected="sellDownValue">
                  </b-form-select>
                </b-form-group>
              </div>
            </div>
            <div class="row">
            </div>
          </div>

          <br>

          <b-button @click.prevent="generateCode" block variant="success" :disabled="genBtn">Generate</b-button>
          <b-button @click.prevent="generateClear" block>Clear</b-button>
          <b-button @click.prevent="generateRandom" block>Random</b-button>
        </div>
        <div class="col-sm-4">
          <b-form-textarea
            id="textarea"
            placeholder="Result"
            no-resize
            :disabled="true"
            rows="12"
            max-rows="6"
            v-model="codeRes"
          ></b-form-textarea>

          <br>

          <b-form-textarea
            id="textarea"
            placeholder="Description"
            no-resize
            :disabled="true"
            rows="6"
            max-rows="6"
            size="sm"
            v-model="codeDes"
          ></b-form-textarea>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
  },

  data() {
    return {
      wrestlerIdValue: false,

      mmmUpValue: false,
      mmmLeftValue: false,
      mmmRightValue: false,
      mmmDownValue: false,
      
      cpUpValue: false,
      cpLeftValue: false,
      cpRightValue: false,
      cpDownValue: false,

      sellUpValue: false,
      sellLeftValue: false,
      sellRightValue: false,
      sellDownValue: false,

      genBtn: false,
      codeRes: '',
      codeDes: '',

      wrestlerId: [
        { value: "0001", text: "Rock (0001)"},
        { value: "0002", text: "SCSA (0002)"},
        { value: "0003", text: "Undertaker (0003)"},
        { value: "0004", text: "Kane (0004)"},
        { value: "0005", text: "Richards (0005)"},
        { value: "0006", text: "Mankind (0006)"},
        { value: "0007", text: "Cactus (0007)"},
        { value: "0008", text: "Mick (0008)"},
        { value: "0009", text: "HBK (0009)"},
        { value: "0101", text: "HHH (0101)"},
        { value: "0102", text: "X-Pac (0102)"},
        { value: "0103", text: "Mr. Ass (0103)"},
        { value: "0104", text: "Road Dogg (0104)"},
        { value: "0201", text: "Benoit (0201)"},
        { value: "0202", text: "Malenko (0202)"},
        { value: "0203", text: "Saturn (0203)"},
        { value: "0204", text: "Guerrero (0204)"},
        { value: "0301", text: "Jericho (0301)"},
        { value: "0302", text: "Angle (0302)"},
        { value: "0303", text: "Tazz (0303)"},
        { value: "0304", text: "Test (0304)"},
        { value: "0305", text: "GodFather (0305)"},
        { value: "0306", text: "D`Lo (0306)"},
        { value: "0307", text: "Venis (0307)"},
        { value: "0308", text: "Shamrock (0308)"},
        { value: "0401", text: "Rikishi (0401)"},
        { value: "0402", text: "Sexay (0402)"},
        { value: "0403", text: "Scotty (0403)"},
        { value: "0404", text: "Edge (0404)"},
        { value: "0405", text: "Christian (0405)"},
        { value: "0406", text: "Matt (0406)"},
        { value: "0407", text: "Jeff (0407)"},
        { value: "0501", text: "Faarooq (0501)"},
        { value: "0502", text: "Bradshaw (0502)"},
        { value: "0503", text: "D-Von (0503)"},
        { value: "0504", text: "Buh Buh (0504)"},
        { value: "0505", text: "Hardcore (0505)"},
        { value: "0506", text: "Crash (0506)"},
        { value: "0507", text: "Bossman (0507)"},
        { value: "0508", text: "Albert (0508)"},
        { value: "0601", text: "Al (0601)"},
        { value: "0602", text: "Blackman (0602)"},
        { value: "0603", text: "Bulldog (0603)"},
        { value: "0604", text: "Henry (0604)"},
        { value: "0605", text: "Viscera (0605)"},
        { value: "0606", text: "Andre (0606)"},
        { value: "0607", text: "Buchanan (0607)"},
        { value: "0608", text: "Rios (0608)"},
        { value: "0609", text: "Taka (0609)"},
        { value: "0701", text: "Chyna (0701)"},
        { value: "0702", text: "Stephanie (0702)"},
        { value: "0703", text: "Tori (0703)"},
        { value: "0704", text: "Debra (0704)"},
        { value: "0705", text: "Trish (0705)"},
        { value: "0706", text: "Lita (0706)"},
        { value: "0801", text: "Jacqueline (0801)"},
        { value: "0802", text: "Linda (0802)"},
        { value: "0803", text: "Kat (0803)"},
        { value: "0804", text: "Moola (0804)"},
        { value: "0805", text: "Ho (0805)"},
        { value: "0901", text: "Vince (0901)"},
        { value: "0902", text: "Shane (0902)"},
        { value: "0903", text: "Hebner (0903)"},
        { value: "0904", text: "Jim Ross (0904)"},
        { value: "0A01", text: "CAW 01 (0A01)"},
        { value: "0A02", text: "CAW 02 (0A02)"},
        { value: "0A03", text: "CAW 03 (0A03)"},
        { value: "0A04", text: "CAW 04 (0A04)"},
        { value: "0A05", text: "CAW 05 (0A05)"},
        { value: "0A06", text: "CAW 06 (0A06)"},
        { value: "0A07", text: "CAW 07 (0A07)"},
        { value: "0A08", text: "CAW 08 (0A08)"},
        { value: "0A09", text: "CAW 09 (0A09)"},
        { value: "0A0A", text: "CAW 10 (0A0A)"},
        { value: "0A0B", text: "CAW 11 (0A0B)"},
        { value: "0A0C", text: "CAW 12 (0A0C)"},
        { value: "0A0D", text: "CAW 13 (0A0D)"},
        { value: "0A0E", text: "CAW 14 (0A0E)"},
        { value: "0A0F", text: "CAW 15 (0A0F)"},
        { value: "0A10", text: "CAW 16 (0A10)"},
        { value: "0A11", text: "CAW 17 (0A11)"},
        { value: "0A12", text: "CAW 18 (0A12)"}
      ],
      masterMoveMods: [
        { value: null, text: "-- Weak Arm Striking", disabled: true },
        { value: "128E", text: `Body Punch` },
        { value: "1298", text: `Chop 01` },
        { value: "12A2", text: `Chop 02` },
        { value: "12AC", text: `Chop 03` },
        { value: "12B6", text: `Elbow Strike` },
        { value: "12C0", text: `Hook Punch 01` },
        { value: "12CA", text: `Hook Punch 02` },
        { value: "12D4", text: `Hook Punch 03` },
        { value: "12DE", text: `Jab` },
        { value: "12E8", text: `Overhand Chop` },
        { value: "12F2", text: `Slap 01` },
        { value: "12FC", text: `Slap 02` },
        { value: "1306", text: `Slap 03` },
        { value: "1310", text: `Slap 04` },
        { value: "131A", text: `Straight Punch` },
        { value: "1324", text: `Woman's Slap `} ,

        { value: null, text: "", disabled: true },
        { value: null, text: "-- Weak Leg Striking", disabled: true },
        { value: "132E", text: `Front Kick 01` },
        { value: "1338", text: `Front Kick 02` },
        { value: "1342", text: `Front Kick 03` },
        { value: "134C", text: `Front Kick 04` },
        { value: "1356", text: `Front Kick 05` },
        { value: "1360", text: `Low Kick 01` },
        { value: "136A", text: `Low Kick 02` },
        { value: "1374", text: `Low Kick 03` },
        { value: "137E", text: `Low Kick 04` },
        { value: "1388", text: `Low Kick 05` },
        { value: "1392", text: `Low Kick 06` },
        { value: "139C", text: `Low Kick 07` },
        { value: "13A6", text: `Low Kick 08` },
        { value: "13B0", text: `Low Kick 09` },
        { value: "13BA", text: `Middle Kick 01` },
        { value: "13C4", text: `Middle Kick 02` },
        { value: "13CE", text: `Middle Kick 03` },
        { value: "13D8", text: `Middle Kick 04` },
        { value: "13E2", text: `Shin Kick to Leg` },
        { value: "13EC", text: `Spinning Crescent Kick `} ,

        { value: null, text: " & Irish Whip Attack", disabled: true },
        { value: null, text: "-- Strong Striking Moves & Irish Whip Attack", disabled: true },
        { value: "15E0", text: `Austin Punch` },
        { value: "15EA", text: `Axe Kick 01` },
        { value: "15F4", text: `Axe Kick 02` },
        { value: "15FE", text: `Axe Kick 03` },
        { value: "1608", text: `Backhand Blow 01` },
        { value: "1612", text: `Backhand Blow 02` },
        { value: "161C", text: `Back Elbow` },
        { value: "1626", text: `Back Spinning Heel Kick` },
        { value: "1630", text: `Back Spinning Wheel Kick` },
        { value: "163A", text: `Big Boot` },
        { value: "1644", text: `Big Kick` },
        { value: "164E", text: `Body Hook Punch` },
        { value: "1658", text: `Bradshaw Hammer` },
        { value: "1662", text: `Buh Buh Punch` },
        { value: "166C", text: `Cheap Shot to Throat` },
        { value: "1676", text: `Chyna Low Blow` },
        { value: "1680", text: `Cyclone Forearm` },
        { value: "168A", text: `Diving Clothesline` },
        { value: "1694", text: `Downward Elbow Strike` },
        { value: "169E", text: `Dragon Fish Blow` },
        { value: "16A8", text: `Dropkick 01` },
        { value: "16B2", text: `Dropkick 02` },
        { value: "16BC", text: `Dropkick to Knee 01` },
        { value: "16C6", text: `Dropkick to Knee 02` },
        { value: "16D0", text: `Dropkick to Knee 03` },
        { value: "16DA", text: `Ear Slap` },
        { value: "16E4", text: `Fast Spinning Wheel Kick` },
        { value: "16EE", text: `Flipping Dropkick` },
        { value: "16F8", text: `Hard Chop 01` },
        { value: "1702", text: `Hard Chop 02` },
        { value: "170C", text: `Hard Headbutt 01` },
        { value: "1716", text: `Hard Headbutt 02` },
        { value: "1720", text: `Hard Headbutt 03` },
        { value: "172A", text: `Haymaker Punch` },
        { value: "1734", text: `Haymaker to Body` },
        { value: "173E", text: `High Spinning Wheel Kick` },
        { value: "1748", text: `Jab L 01` },
        { value: "1752", text: `Jab L 02` },
        { value: "175C", text: `Jab R` },
        { value: "1766", text: `Jumping Axe Kick` },
        { value: "1770", text: `Jumping Clothesline` },
        { value: "177A", text: `Jumping Front Dropkick` },
        { value: "1784", text: `Jumping Karate Kick` },
        { value: "178E", text: `Jumping Knee Strike` },
        { value: "1798", text: `Jumping Spinning Roundhouse` },
        { value: "17A2", text: `Jump Crescent Kick` },
        { value: "17AC", text: `Jump Spinning Hook Kick` },
        { value: "17B6", text: `Spin Back Kick` },
        { value: "17C0", text: `Round Dropkick 01` },
        { value: "17CA", text: `Round Dropkick 02` },
        { value: "17D4", text: `Round Dropkick 03` },
        { value: "17DE", text: `Round Dropkick 04` },
        { value: "17E8", text: `Jump Roundhouse Kick` },
        { value: "17F2", text: `Kung Fu Strike 01` },
        { value: "17FC", text: `Kung Fu Strike 02` },
        { value: "1806", text: `Low Drop Roundhouse Kick` },
        { value: "1810", text: `Low Spin Back Kick` },
        { value: "181A", text: `Mongolian Chop` },
        { value: "1824", text: `Palm Strike` },
        { value: "182E", text: `Pimp Lariat` },
        { value: "1838", text: `Punch 01` },
        { value: "1842", text: `Punch 02` },
        { value: "184C", text: `Punch 03` },
        { value: "1856", text: `Punch 04` },
        { value: "1860", text: `Punch 05` },
        { value: "186A", text: `Punch 06` },
        { value: "1874", text: `Punch 07` },
        { value: "187E", text: `President Slap` },
        { value: "1888", text: `Rikishi Punch` },
        { value: "1892", text: `Rikishi Sidekick` },
        { value: "189C", text: `Road Dogg Jab` },
        { value: "18A6", text: `Rock Punch` },
        { value: "18B0", text: `Rolling Back Kick` },
        { value: "18BA", text: `Roundhouse High Kick L 01` },
        { value: "18C4", text: `Roundhouse High Kick L 02` },
        { value: "18CE", text: `Roundhouse High Kick R 01` },
        { value: "18D8", text: `Roundhouse High Kick R 02` },
        { value: "18E2", text: `Roundhouse High Kick R 03` },
        { value: "18EC", text: `Roundhouse Mid Kick 01` },
        { value: "18F6", text: `Roundhouse Mid Kick 02` },
        { value: "1900", text: `Roundhouse Mid Kick 03` },
        { value: "190A", text: `Russian Hook Punch` },
        { value: "1914", text: `Shouda 01` },
        { value: "191E", text: `Shouda 02` },
        { value: "1928", text: `Shouda 03` },
        { value: "1932", text: `Shuffle Hook Kick` },
        { value: "193C", text: `Sidekick 01` },
        { value: "1946", text: `Sidekick 02` },
        { value: "1950", text: `Sidekick 03` },
        { value: "195A", text: `Somersault Kick` },
        { value: "1964", text: `Spinning Back Chop 01` },
        { value: "196E", text: `Spinning Back Chop 02` },
        { value: "1978", text: `Spinning Back Elbow` },
        { value: "1982", text: `Spinning Back Kick 01` },
        { value: "198C", text: `Spinning Back Kick 02` },
        { value: "1996", text: `Spinning Back Kick 03` },
        { value: "19A0", text: `Spinning Back Kick 04` },
        { value: "19AA", text: `Spinning Clothesline` },
        { value: "19B4", text: `Spinning Elbow` },
        { value: "19BE", text: `Spinning Leg Sweep` },
        { value: "19C8", text: `Spinning Wheel Kick 01` },
        { value: "19D2", text: `Spinning Wheel Kick 02` },
        { value: "19DC", text: `Standing Clothesline 01` },
        { value: "19E6", text: `Standing Clothesline 02` },
        { value: "19F0", text: `Thai Roundhouse Kick L` },
        { value: "19FA", text: `Thai Roundhouse Kick R` },
        { value: "1A04", text: `Throat Thrust 01` },
        { value: "1A0E", text: `Throat Thrust 02` },
        { value: "1A18", text: `Thrusting Knee Sidekick` },
        { value: "1A22", text: `Undertaker Punch` },
        { value: "1A2C", text: `X-Pac Kick` },
        { value: "1A36", text: `Uppercut 01` },
        { value: "1A40", text: `Uppercut 02` },
        { value: "1A4A", text: `Uppercut 03` },
        { value: "1A54", text: `Uppercut 04` },
        { value: "1A5E", text: `Uppercut 05` },
        { value: "1A68", text: `Vince Slap` },
        { value: "1A72", text: `Woman's Hard Slap L` },
        { value: "1A7C", text: `Woman's Hard Slap R` },
        { value: "1A86", text: `Yakuza Kick` },
        { value: "1A90", text: `3-Point Stance Charge` },
       ],
       connectionPoints: [
        { value: "0504", text: "Headbutt" },
        { value: "0A09", text: "Left Arm" },
        { value: "1112", text: "Right Arm" },
        { value: "0608", text: "Left Leg" },
        { value: "0F0D", text: "Right Leg" },
        { value: "1109", text: "Double hands " },
        { value: "080F", text: "Double legs (Dropkick)" },
       ],
       sellAnimations: [
        { value: "0000", text: "Strike to face (Slap)" },
        { value: "0001", text: "Strike to chest (Chop)" },
        { value: "0002", text: "Normal kick" },
        { value: "0003", text: "Strike to leg" },
        { value: "0004", text: "Low Blow" },
        { value: "0005", text: "Body Punch" },
       ],
    }
  },

  methods: {
    generateCode() {
      let btnListSrc = []

      const btnList = [
        { dir: '4800', value: this.mmmUpValue, sell: this.sellUpValue, cp: this.cpUpValue },
        { dir: '4200', value: this.mmmLeftValue, sell: this.sellLeftValue, cp: this.cpLeftValue },
        { dir: '4100', value: this.mmmRightValue, sell: this.sellRightValue, cp: this.cpRightValue },
        { dir: '4400', value: this.mmmDownValue, sell: this.sellDownValue, cp: this.cpDownValue } ]

      btnList.forEach(btn => {
        btnListSrc.push(`
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          810910FA-${btn.value}
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          810910FE-${btn.value}
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          800ACE25-${btn.sell}
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          800ACE6D-${btn.sell}
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          800ACE21-${btn.cp}
          D115AF50-${this.wrestlerIdValue}
          D1064880-${btn.dir}
          800ACE69-${btn.cp}
          
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          81091542-${btn.value}
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          81091546-${btn.value}
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          800B1B35-${btn.sell}
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          800B1B7D-${btn.sell}
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          800B1B31-${btn.cp}
          D115B2A8-${this.wrestlerIdValue}
          D1064886-${btn.dir}
          800B1B79-${btn.cp}`)
      })

      let rawCode = btnListSrc.join('').toUpperCase()

      // REMOVE SPACES
      rawCode = rawCode.replace(/\s/g,'')

      // ADD BREAKLINES
      let n = 13
      let explodeArr = []

      for(let i = 0; i < rawCode.length; i += n) {
        explodeArr.push(rawCode.substr(i, n))
      }
      rawCode = explodeArr.join('\n').replace(/-/g,' ')

      this.codeRes = rawCode


      // Description
      let wrestler = this.wrestlerId.find(el => {
        return el.value == this.wrestlerIdValue
      })
      let descrUp = this.masterMoveMods.find(el => {
        return el.value == this.mmmUpValue
      })
      let descrLeft = this.masterMoveMods.find(el => {
        return el.value == this.mmmLeftValue
      })
      let descrRight = this.masterMoveMods.find(el => {
        return el.value == this.mmmRightValue
      })
      let descrDown = this.masterMoveMods.find(el => {
        return el.value == this.mmmDownValue
      })

      let moveSet = 
        `Replaces: ${wrestler.text}  \n\nB + Up: ${descrUp.text} \nB + Left: ${descrLeft.text} \nB + Right: ${descrRight.text} \nB + Down: ${descrDown.text}`

      this.codeDes = moveSet
    },

    generateClear() {
      this.wrestlerIdValue = false
      this.mmmUpValue = false
      this.mmmLeftValue = false
      this.mmmRightValue = false
      this.mmmDownValue = false

      this.sellUpValue = false
      this.sellLeftValue = false
      this.sellRightValue = false
      this.sellDownValue = false

      this.cpUpValue = false
      this.cpLeftValue = false
      this.cpRightValue = false
      this.cpDownValue = false
    },

    generateRandom() {
      this.wrestlerIdValue = this.wrestlerId[Math.floor(Math.random() * (this.wrestlerId.length - 1)) + 1].value

      this.mmmUpValue = this.masterMoveMods[Math.floor(Math.random() * (this.masterMoveMods.length - 1)) + 1].value
      this.mmmLeftValue = this.masterMoveMods[Math.floor(Math.random() * (this.masterMoveMods.length - 1)) + 1].value
      this.mmmRightValue = this.masterMoveMods[Math.floor(Math.random() * (this.masterMoveMods.length - 1)) + 1].value
      this.mmmDownValue = this.masterMoveMods[Math.floor(Math.random() * (this.masterMoveMods.length - 1)) + 1].value

      this.sellUpValue = this.sellAnimations[Math.floor(Math.random() * (this.sellAnimations.length - 1)) + 1].value
      this.sellLeftValue = this.sellAnimations[Math.floor(Math.random() * (this.sellAnimations.length - 1)) + 1].value
      this.sellRightValue = this.sellAnimations[Math.floor(Math.random() * (this.sellAnimations.length - 1)) + 1].value
      this.sellDownValue = this.sellAnimations[Math.floor(Math.random() * (this.sellAnimations.length - 1)) + 1].value

      this.cpUpValue = this.connectionPoints[Math.floor(Math.random() * (this.connectionPoints.length - 1)) + 1].value
      this.cpLeftValue = this.connectionPoints[Math.floor(Math.random() * (this.connectionPoints.length - 1)) + 1].value
      this.cpRightValue = this.connectionPoints[Math.floor(Math.random() * (this.connectionPoints.length - 1)) + 1].value
      this.cpDownValue = this.connectionPoints[Math.floor(Math.random() * (this.connectionPoints.length - 1)) + 1].value
    },

    // isHex(evt) {
    //   evt = (evt) ? evt : window.event;
    //   let charCode = (evt.which) ? evt.which : evt.keyCode;
    //   if ((charCode >= 48 && charCode <= 57) || (charCode >= 97 && charCode <= 102)) {
    //     return true;
    //   } else {
    //     evt.preventDefault();
    //   }
    // },

    checkValues() {
      if((this.wrestlerIdValue != false) &&
      (this.mmmUpValue != false) &&
      (this.mmmLeftValue != false) &&
      (this.mmmRightValue != false) &&
      (this.mmmDownValue != false) &&
      (this.sellUpValue != false) &&
      (this.sellLeftValue != false) &&
      (this.sellRightValue != false) &&
      (this.sellDownValue != false) &&
      (this.cpUpValue != false) &&
      (this.cpLeftValue != false) &&
      (this.cpRightValue != false) &&
      (this.cpDownValue != false)) {
        this.genBtn = false
      } else {
        this.genBtn = true
      }
    }
  },

  // watch: {
  //   wrestlerIdValue() {
  //     this.checkValues()
  //   },

  //   mmmUpValue() {
  //     this.checkValues()
  //   },

  //   mmmLeftValue() {
  //     this.checkValues()
  //   },

  //   mmmRightValue() {
  //     this.checkValues()
  //   },

  //   mmmDownValue() {
  //     this.checkValues()
  //   },

  //   sellUpValue() {
  //     this.checkValues()
  //   },

  //   sellLeftValue() {
  //     this.checkValues()
  //   },

  //   sellRightValue() {
  //     this.checkValues()
  //   },

  //   sellDownValue() {
  //     this.checkValues()
  //   },

  //   cpUpValue() {
  //     this.checkValues()
  //   },

  //   cpLeftValue() {
  //     this.checkValues()
  //   },

  //   cpRightValue() {
  //     this.checkValues()
  //   },

  //   cpDownValue() {
  //     this.checkValues()
  //   }
  // }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
