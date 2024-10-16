<script>
export default {
  name: "App",
  data() {
    return {
      radius: 0,
      message: "",
      textColor: "",
      bgColor: "#CBC3E3",
      showText: true,
      size: "12px",
      opacity: "",
      fonts: ["cursive", "monospace", "menlo"],
      selectedFont: "",
    };
  },
};
</script>

<template>
  <div id="app">
    <div class="container mt-5">
      <div class="row">
        <div class="col-sm-5">
          <div id="squareSettings">
            <div class="mb-3">
              <label for>Color de fondo:</label>
              <input v-model="bgColor" type="text" id="inputWidth" />
            </div>
            <div class="mb-3">
              <label for>Color de texto:</label>
              <input v-model="textColor" type="text" id="inputWidth" />
            </div>
            <div class="mb-3">
              <label class="me-2" for="cbox2">Mostrar texto</label>
              <input v-model="showText" type="checkbox" />
            </div>
            <div class="mb-3">
              <label for>Borde</label><br />
              <input v-model="radius" type="range" min="0" max="180" id="inputWidth"/>
            </div>
            <div class="mb-3">
              <label for>Contenido textual</label>
              <textarea v-model="message" id="inputWidth"></textarea>
            </div>
            <div class="mb-3">
              <label for>Tipografía</label>
              <select v-model="selectedFont" id="inputWidth">
                <option v-for="font in fonts" :key="font" :value="font">
                  {{ font }}
                </option>
              </select>
            </div>
            <div class="mb-3">
              <label for class="me-2">Opaco</label>
              <input v-model="opacity" type="checkbox" id="opacity" value="opacity"/><br />
            </div>
            <div class="mb-3">
              <label for>Tamaño de letra</label><br />
              <input v-model="size" type="radio" id="pequeño" value="10px" />
              <label class="mx-2" for="mediano">Pequeño</label>
              <input v-model="size" type="radio" id="mediano" value="24px" />
              <label class="mx-2" for="mediano">Mediano</label>
              <input v-model="size" type="radio" id="grande" value="60px" />
              <label class="mx-2" for="grande">Grande</label>
            </div>
          </div>
        </div>
        <div class="col-sm-7 d-flex align-items-center justify-content-center">
          <div :style="{ borderRadius: radius + 'px', backgroundColor: bgColor, fontSize: size, }" :class="{ opacity: opacity }"
            id="square">
            <p v-show="showText" :style="{ color: textColor, fontFamily: selectedFont }">{{ message }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
#squareSettings {
  background-color: #ebe8fc;
  padding: 2rem;
  border-radius: 40px;
  box-shadow: -9px 10px 21px -1px rgba(162, 122, 191, 0.69);
}

#inputWidth {
  width: 450px;
}

#square {
  width: 350px;
  height: 350px;
  display: flex;
  align-items: center;
  justify-content: center;
  word-break: break-all;
}

.opacity {
  opacity: 0.5;
}
</style>
