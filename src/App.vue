<template>
  <div class="container">
    <div class="row">
      <h1 class="text-center" style="margin-bottom: 30px">v-bind with $attrs</h1>

      <div class="panel panel-default">
        <div class="panel-heading">
          <h2>What is the instance property "$attrs"?</h2>
        </div>
        <div class="panel-body">
          <p>
            A VueJs object containing the parent element's attributes that are not declared as props (Not including class / style).
          </p>
          <a href="https://vuejs.org/v2/api/?#vm-attrs">View definition on vue.js</a>
        </div>
      </div>

      <div class="panel panel-default">
        <div class="panel-heading">
          <h2>What does the "inheritAttrs" property do?</h2>
        </div>
        <div class="panel-body">
          <p>
            By default, all parent attributes are binded to the root element of the child component (in this case, the label). <br>
            When we want to attach these attributes to different elements in the child component, we can set inheritAttrs to false and assign them manually to the elements we want to by choise.
          </p>
          <a href="https://vuejs.org/v2/api/?#inheritAttrs">View definition on vue.js</a>
          <img src="./assets/example.png" alt="example" class="img-responsive">
        </div>
      </div>

      <div class="panel panel-default">
        <div class="panel-heading">
          <h2>What are we going to look at?</h2>
          <ul>
            <p>Split attributes between several elements (label and input) - as props or $attrs?</p>
          </ul>
        </div>
        <div class="panel-body">
          <div class="col-md-12" style="margin-bottom: 30px; border-bottom: 3px dotted lightgray">
            <p><strong>Input attributes:</strong></p>
            <ul>
              <li>placeholder</li>
              <li>value</li>
              <li>name</li>
            </ul>
            <br><br>
            <p><strong>Additional attributes:</strong></p>
            <ul>
              <li>label</li>
              <li>test</li>
              <li>anotherAttr</li>
            </ul>
          </div>
          <div class="col-md-12 AppComponent">
            <div class="col-md-12 panel panel-default withoutAttrs">
              <h4><strong>inheritAttrs=false</strong></h4>
              <hr>
              <app-parent 
              :withInheritAttrs="false" 
              :label="'Username'" 
              :test="true" 
              :anotherAttr="true" 
              :placeholder="placeholder" 
              :value="value" 
              :name="name"></app-parent>

              <div class="col-md-12 col-xs-12">
              <hr>
                <h4><strong>Parent component:</strong></h4>
                <h5>{{exampleOne}}</h5>
              </div>
            </div>
            <div class="col-md-12 panel panel-default withInheritAttrs">
              <h4><strong>inheritAttrs=true</strong></h4>
              <hr>
              <app-parent 
              :withInheritAttrs="true" 
              :label="'Username'" 
              :test="true" 
              :anotherAttr="true" 
              :placeholder="placeholder" 
              :value="value" 
              :name="name"></app-parent>
              <div class="col-md-12 col-xs-12">
              <hr>
                <h4><strong>Parent component:</strong></h4>
                <h5>{{exampleTwo}}</h5>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Parent from './components/examples/Parent'
export default {
  name: 'app',
  components: {
    'app-parent': Parent
  },
  data () {
    return {
      placeholder: 'Type in your name',
      value: 'Tom',
      name: 'username',
      exampleOne: `<app-parent 
              :withInheritAttrs="false" 
              :label="'Username'" 
              :test="true" 
              :anotherAttr="true" 
              :placeholder="placeholder" 
              :value="value" 
              :name="name"></app-parent>`,
      exampleTwo: `<app-parent 
              :withInheritAttrs="true" 
              :label="'Username'" 
              :test="true" 
              :anotherAttr="true" 
              :placeholder="placeholder" 
              :value="value" 
              :name="name"></app-parent>`
    }
  }
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

h1, h2 {
  font-weight: normal;
}

p, a {
  font-size: 18px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
