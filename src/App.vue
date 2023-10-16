<script>
  export default {
    data: () => {
      return{
        products: [
          {
            id: 1,
            title: 'Airpods Pro (2ND GENERATION)',
            description: 'Второе поколение AirPods Pro сочетает в себе всё, за что миллионы пользователей полюбили эти наушники: отличный звук, удобную посадку, систему активного шумоподавления, удобное подключение к устройствам Apple с возможностью автоматического переключения между ними и другие приятные мелочи, а также новые особенности, которые призваны обеспечить максимум комфорта и удовольствия: новый кейс с отверстием для шнурка и поддержкой магнитной и беспроводной зарядки, передовую систему пространственного звучания и улучшенное сенсорное управление, которое теперь поддерживает "свайпы".',
            price: '133 990тг',
            src: 'https://object.pscloud.io/cms/cms/Photo/img_0_83_1263_0_6.png'
          },
          {
            id: 2,
            title: 'Airpods Pro (2ND GENERATION)',
            description: 'Второе поколение AirPods Pro сочетает в себе всё, за что миллионы пользователей полюбили эти наушники: отличный звук, удобную посадку, систему активного шумоподавления, удобное подключение к устройствам Apple с возможностью автоматического переключения между ними и другие приятные мелочи, а также новые особенности, которые призваны обеспечить максимум комфорта и удовольствия: новый кейс с отверстием для шнурка и поддержкой магнитной и беспроводной зарядки, передовую систему пространственного звучания и улучшенное сенсорное управление, которое теперь поддерживает "свайпы".',
            price: '133 990тг',
            src: 'https://object.pscloud.io/cms/cms/Photo/img_0_83_1263_0_6.png'
          }
        ],
        inputName: '',
        inputAge: '',
        colors: [
          { name:"red", hex:"#d42828" },
          { name:"yellow", hex:"#d4ce28" },
          { name:"green", hex:"#5cd428" },
          { name:"lightblue", hex:"#28d4d4" },
          { name:"darkblue", hex:"#2842d4" },
          { name:"purple", hex:"#8928d4" },
          { name:"pink", hex:"#d4289d" },
        ],
        color_box: 'color_box',
        textareaText: '',
        isFormatted: false,
      }
    },
    methods: {
      formateText(){
        this.isFormatted = true
      }
    }
  }
</script>

<template>
  <h1>1 задание</h1>
  <hr>
  <div>
    <div v-for="product in products" :key="product.id">
      <img :src="product.src" alt="" width="200" height="200" />
      <h3>{{product.title}}</h3>
      <p>{{product.description}}</p>
      <h3>{{product.price}}</h3>
    </div>
  </div>

  <br>
  <h1>2 задание</h1>
  <hr>
  <br>

  <div>
    <input type="text" placeholder="Ваше имя" v-model="inputName" >
    <input type="number" placeholder="Ваш возраст" v-model="inputAge" >
    <p v-if="inputAge<=0">Ваш возраст не может быть меньше 0</p>
    <p v-else-if="inputAge>0 && inputAge<18">Вам нет 18</p>
    <p v-else>Вы старый</p>
  </div>

  <br>
  <h1>3 задание</h1>
  <hr>
  <br>

  <div class='flex' >
    <div v-for="color, key in colors" :key="key">
      <div class="size">
        <div :class="[color_box, color.name]"></div>
        <p>{{color.name}}</p>
        <p>{{color.hex}}</p>
      </div>
    </div>
  </div>

  <br>
  <h1>4 задание</h1>
  <hr>
  <br>

  <div>
    <textarea v-model="textareaText" @input="formateText"></textarea>
    <div>
      <p :class="{ boldAndItalic: isFormatted }">{{textareaText}}</p>
    </div>
  </div>
  
</template>

<style scoped>
  .flex{
    display:flex;
  }
  .size{
    width: 100px;
    height: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .color_box{
    width: 50px;
    height: 50px;
  }
  .red{
    background-color:#d42828;
  }
  .yellow{
    background-color:#d4ce28;
  }
  .green{
    background-color:#5cd428;
  }
  .lightblue{
    background-color:#28d4d4;
  }
  .darkblue{
    background-color:#2842d4;
  }
  .purple{
    background-color:#8928d4;
  }
  .pink{
    background-color:#d4289d;
  }
  .boldAndItalic {
    font-weight: bold;
    font-style: italic;
  }
</style>
