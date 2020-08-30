<template>
  <div>
    <div id="bt" class="row">
      <div id="aa" class="col">
        <button id="bb1" @click="start()">Start</button>
      </div>
      <div id="aa" class="col">
        <button id="bb2" v-bind:disabled="end" @click="attack()">Attack</button>
      </div>
      <div id="aa" class="col">
        <button id="bb3" v-bind:disabled="end" @click="special()">Special attack</button>
      </div>
      <div id="aa" class="col">
        <button id="bb4" @click="reset()">Play again</button>
      </div>
    </div>     
      <br />
      <br />
      <br />
      <br />
      <br />
      <br />

    <div class="row">
      <div class="col-sm">
        <p style="font-size: 150%">{{aplayer.name}}</p>
        <p>
          <img v-bind:style="{width: aplayer.hp + 'px'}" :src="hp1" alt height="20px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{aplayer.hp}}</p>
        <p>
          <img style="width:300px" :src="aplayer.image" />
        </p>
      </div>
      <div class="row">
        <div class="col"></div>
        <div class="col"></div>
      </div>

      <div class="row">
        <div class="col-sm"></div>
        <div class="col-sm">
          <div id="score">
            <div v-if="amonster.hp <= 0">
              <FONT color="black">"You Win"</FONT>
            </div>
            <div v-else-if="aplayer.hp <= 0">
              <FONT color="black">You lose</FONT>
            </div>
          </div>
        </div>
        <div class="col-sm"></div>
      </div>
    </div>
    <br />
    <br />

    <img
      src="https://us.123rf.com/450wm/bridddy/bridddy1508/bridddy150800686/44501626-blue-neon-versus-logo-vs-vector-letters-illustration-competition-icon-fight-symbol-.jpg?ver=6"
      width="50%"
    />
    <br />
    <br />
    <br />
    <div class="col-sm">
      <p style="font-size: 150%">{{amonster.name}}</p>
      <p>
        <img v-bind:style="{width: amonster.hp + 'px'}" :src="hp2" alt height="15px" />
      </p>
      <p style="font-size: 150%">{{thp}}{{amonster.hp}}</p>
      <p>
        <img style="width:300px" :src="amonster.image" />
      </p>
    </div>
    <br />
    <br />
    <br />
    <br />
    <br />
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      thp: "HP:",
      end: false,
      hp2:
        "https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67",
      hp1:
        "https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67",
      aplayer: { name: "", hp: 1, image: "", hp1: "" },
      player: [
        {
          name: "Thor",
          hp: 470,
          image:
            "https://sites.google.com/site/sakdaphoda/_/rsrc/1488269903657/thor/t1.png",
        },
        {
          name: "Captain America",
          hp: 450,
          image:
            "https://pngimg.com/uploads/captain_america/captain_america_PNG57.png",
        },
        {
          name: "Spiderman",
          hp: 350,
          image: "https://cs.lnwfile.com/vtaah6.png",
        },
        {
          name: "Ironman",
          hp: 500,
          image: "https://cs.lnwfile.com/7jwklq.png",
        },
        {
          name: "Hulk",
          hp: 550,
          image:
            "https://sites.google.com/site/sirilak044618/_/rsrc/1440344163329/home/the-hulk/hulk_png_render_from_aou_by_joaohbd-d8knjyv.png",
        },
        {
          name: "Natasha",
          hp: 400,
          image:
            "https://i.pinimg.com/originals/4c/d8/83/4cd88308b150a4b76b49b4b08f96c278.png",
        },
      ],
      amonster: { name: "", hp: 1, image: "", hp1: "" },
      monster: [
        {
          name: "Thanos",
          hp: 700,
          image:
            "https://vignette.wikia.nocookie.net/mugen/images/1/18/MUA3_Thanos.png/revision/latest/scale-to-width-down/340?cb=20190904195520",
        },
        {
          name: "Red Skull",
          hp: 350,
          image:
            "https://lh3.googleusercontent.com/proxy/s1v2HfdfaL7WxGEFEps4wdqT1h0Ms9ypUCbVPEF5qxrwfQ1_1GTq9cVVve9msFQmyGhUmWPBuwZtlrigTWyJ7qmltClvhOwSiWvJsYdT61pvUXv1jsxMq8dBST1xh1boF-RsBUqMAZaDuOcPe6E",
        },
        {
          name: "Hela",
          hp: 480,
          image:
            "https://i.pinimg.com/originals/87/8d/c8/878dc8a4728248cc91ccebb1f44bf014.png",
        },
        {
          name: "Ultron",
          hp: 300,
          image:
            "https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/3a1b02a9-0ca7-4130-810e-c6db42004a20/d8knl1k-16874327-4abd-479e-bf7d-725e88b4dd1e.png/v1/fill/w_600,h_909,strp/ultron_png_render_from_marvel_s_the_avengers_aou_by_joaohbd_d8knl1k-fullview.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3siaGVpZ2h0IjoiPD05MDkiLCJwYXRoIjoiXC9mXC8zYTFiMDJhOS0wY2E3LTQxMzAtODEwZS1jNmRiNDIwMDRhMjBcL2Q4a25sMWstMTY4NzQzMjctNGFiZC00NzllLWJmN2QtNzI1ZTg4YjRkZDFlLnBuZyIsIndpZHRoIjoiPD02MDAifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6aW1hZ2Uub3BlcmF0aW9ucyJdfQ.0kRgH94X4NlB4xnVUoOqlajMiYKYNS79_RtDHs18oeo",
        },
        {
          name: "Loki",
          hp: 420,
          image:
            "https://i.pinimg.com/originals/d0/2c/be/d02cbe25880a02017853b8ad68f19025.png",
        },
        {
          name: "Ronan",
          hp: 400,
          image:
            "https://vignette.wikia.nocookie.net/outlier-battles/images/5/53/Ronan_the_accuser_render_by_franky4fingersx2-d7nihy9.png/revision/latest/scale-to-width-down/340?cb=20180828091959",
        },
      ],
      player_max: "",
      monster_max: "",
    };
  },
  methods: {
    randomno: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      this.aplayer = this.player[this.randomno(1, 5) - 1];
      this.amonster = this.monster[this.randomno(1, 6) - 1];
    },
    attack: function () {
      this.player_max = Math.floor(Math.random() * 7 + 3);
      this.amonster.hp = this.amonster.hp - this.player_max;
      this.monster_max = Math.floor(Math.random() * 10 + 3);
      this.aplayer.hp = this.aplayer.hp - this.monster_max;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    special: function () {
      this.player_max = Math.floor(Math.random() * 20 + 6);
      this.amonster.hp = this.amonster.hp - this.player_max;
      this.monster_max = Math.floor(Math.random() * 13 + 6);
      this.aplayer.hp = this.aplayer.hp - this.monster_max;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    reset: function () {
      window.location.reload();
    },
  },
};
</script>
<style>
#score {
  font-size: 500%;
  color: aliceblue;
}
#aa {
  display: inline;
  padding: 50px;
  widows: 0px;
  font-size: 20px;
  font-weight: bold;
}
#bt {
  padding: 0px;
  justify-content: center;
  display: flex;
  margin: 0x;
  list-style-type: none;
}
#bb1 {
  border-radius: 30px;
  width: 200px;
  height: 60px;
  background-color: rgb(240, 11, 11);
}
#bb2 {
  border-radius: 30px;
  width: 200px;
  height: 50px;
  background-color: rgb(172, 172, 172);
}
#bb3 {
  border-radius: 30px;
  width: 200px;
  height: 50px;
  background-color: rgb(172, 172, 172);
}
#bb4 {
  border-radius: 30px;
  width: 200px;
  height: 50px;
  background-color: rgb(12, 21, 136);
}
</style>