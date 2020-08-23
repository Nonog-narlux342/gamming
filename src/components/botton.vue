<template>
  <div>
    <div class="row">
      <div class="col-sm">
        <p style="font-size: 150%">{{aplayer.name}}</p>
        <p>
          <img v-bind:style="{width: aplayer.hp + 'px'}" :src="hp1" alt height="20px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{aplayer.hp}}</p>
        <p>
          <img style="width:80%" :src="aplayer.image" />
        </p>
      </div>
      <div class="col-sm">
        <div class="row">
          <div class="col">
            <button class="btn btn-primary" @click="start()">Start</button>
          </div>
          <div class="col">
            <button v-bind:disabled="end" class="btn btn-danger" @click="attack()">Attack</button>
          </div>
          <div class="col-4">
            <button v-bind:disabled="end" class="btn btn-dark" @click="special()">SpecialAttack</button>
          </div>
          <div class="col">
            <button class="btn btn-light" @click="reset()">NewGame</button>
          </div>
          <br />
          <img
            src="https://www.freepngimg.com/thumb/animation/84267-versus-of-wallpaper-diagram-computer-witcher-geralt.png"
            width="100%"
          />
        </div>
        <div class="row">
          <div class="col-sm"></div>
          <div class="col-sm">
            <div id="score">
              <div v-if="amonster.hp <= 0">You Win</div>
              <div v-else-if="aplayer.hp <= 0">You Lose</div>
            </div>
          </div>
          <div class="col-sm"></div>
        </div>
      </div>
      <div class="col-sm">
        <p style="font-size: 150%">{{amonster.name}}</p>
        <p>
          <img v-bind:style="{width: amonster.hp + 'px'}" :src="hp2" alt height="15px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{amonster.hp}}</p>
        <p>
          <img style="width:80%" :src="amonster.image" />
        </p>
      </div>
    </div>
    <hr />
    <div class="row">
      <div class="col"></div>
      <div class="col-6">
        <div class="card bg-light">
          <div class="card-header">How to Play</div>
          <div class="card-body">
            <p>1.กดปุ่ม Start เพื่อทําการ Ramdom ตัวละครทั้ง 2 ฝ่าย</p>
            <p>2.ดปุ่ม Attack เพื่อทำ Damage โจมตีเบาใส่อีกฝ่ายและถูกโจมตีในเวลาเดียวกัน</p>
            <p>3.กดปุ่ม Special Attack เพื่อทำ Damage โจมตีหนักใส่อีกฝ่ายและถูกโจมตีในเวลาเดียวกัน</p>
            <p>4.กดปุ่ม New Game เพื่อทําการเริมเล่นเกมใหม่</p>
          </div>
        </div>
      </div>
      <div class="col"></div>
    </div>
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
          name: "Lunastra",
          hp: 380,
          image:
            "http://www.pngmart.com/files/7/Monster-Hunter-World-Transparent-PNG.png",
        },
        {
          name: "Meliodas",
          hp: 330,
          image:
            "http://www.pngmart.com/files/12/The-Seven-Deadly-Sins-Meliodas-PNG-Image.png",
        },
        {
          name: "Olaf Frozen",
          hp: 130,
          image:
            "https://www.freepngimg.com/thumb/frozen/28780-4-frozen-olaf-transparent-image.png",
        },
        {
          name: "Master Oogway",
          hp: 330,
          image:
            "https://www.freepngimg.com/thumb/kung_fu_panda/9-2-kung-fu-panda-turtle-png.png",
        },
        {
          name: "Saitama",
          hp: 500,
          image: "http://www.pngmart.com/files/5/One-Punch-PNG-Transparent.png",
        },
        {
          name: "Broly",
          hp: 250,
          image: "http://www.pngmart.com/files/4/Dragon-Ball-Broly-PNG-Pic.png",
        },
        {
          name: "Kirito",
          hp: 250,
          image:
            "http://www.pngmart.com/files/13/Kazuto-Kirigaya-Kirito-PNG-File.png",
        },
      ],
      amonster: { name: "", hp: 1, image: "", hp1: "" },
      monster: [
        {
          name: "Godzilla",
          hp: 500,
          image:
            "https://www.freepngimg.com/thumb/godzilla/3-2-godzilla-free-download-png.png",
        },
        {
          name: "Chicken Minecraft",
          hp: 120,
          image:
            "https://www.freepngimg.com/thumb/minecraft/1-2-minecraft-chicken-png.png",
        },
        {
          name: "Sesshomaru",
          hp: 215,
          image:
            "http://www.pngmart.com/files/4/Inuyasha-PNG-Transparent-Picture.png",
        },
        {
          name: "Reborn",
          hp: 325,
          image: "http://www.pngmart.com/files/5/Reborn-PNG-HD.png",
        },
        {
          name: "Dah'ren Mohran",
          hp: 385,
          image: "http://www.pngmart.com/files/4/Sand-Monster-PNG-Photos.png",
        },
        {
          name: "Monkey D Luffy",
          hp: 225,
          image: "http://www.pngmart.com/files/2/Monkey-D-Luffy-PNG-Photos.png",
        },
        {
          name: "Deidara",
          hp: 230,
          image:
            "http://www.pngmart.com/files/13/Naruto-Akatsuki-PNG-Transparent.png",
        },
      ],
      pmax: "",
      mmax: "",
    };
  },
  methods: {
    randomno: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      this.aplayer = this.player[this.randomno(1, 7) - 1];
      this.amonster = this.monster[this.randomno(1, 7) - 1];
    },
    attack: function () {
      this.pmax = Math.floor(Math.random() * 10 + 4);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 10 + 4);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    special: function () {
      this.pmax = Math.floor(Math.random() * 15 + 6);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 15 + 6);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
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
  font-size: 300%;
  color: aliceblue;
}
</style>