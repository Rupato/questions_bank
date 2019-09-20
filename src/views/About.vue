<template>
    <div class="row">
      <div class="col-md-3"></div>
       <div class="col-md-6">
         <div class="card background_for_card">
           <form @submit="formSubmit">
           <div class="row">
                <div class="col-md-1"></div>
                <div class="col-md-10">
                  <p class="align_left font">Form Name</p>
                  <input type="text" class="form-control" v-model="name">
                    <p class="align_left font">Form Description</p>
                  <input type="text" class="form-control" v-model="summary">
                  <p class="align_left font">Scenario</p>
                   <vue-editor v-model="content"></vue-editor>
                  <!-- <Editor /> -->
                  
                  <div class="row">
                    <div class="col-lg-10">       
                    </div>
                     <div class="col-lg-2">
                  <button type="submit" class="btn btn-primary" id="dataSave">Save</button>
                    </div>
                  </div>
                </div>
                <div class="col-md-1"></div>
             </div>
           </form>
         </div>
       </div>
         <div class="col-md-3"></div>
    </div>
</template>


<script type="text/javascript">
import { VueEditor, Quill } from "vue2-editor";
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; 
import '../../public/styles.css';
//import { quillEditor } from "vue-quill-editor"; //Call the Editor

import Editor from '@/components/Editor.vue';

// @ is an alias to /src

export default ({
   name: "richText",

   mounted() {
            console.log('Component mounted.')
        },
  components: {
         VueEditor,
        // quillEditor,
        Editor
  },
  // props:['content'], 
  data(){
  // let Delta = this.$refs.qc.$el.querySelector('.ql-editor').innerHTML;
    return{
      name : '',
      summary :  '',
      situationId: 1,
      scenarioId: 1,
      config: "",
      statements:  "",
      content:  '<p>Some initial content</p>',
      delta: '<p>Some initial content</p>',
      config: '',
      content: '<p>Some initial content</p>',
      content1: '<p>Some initial content</p>',
      content2: '<p>Some initial content</p>',
      content3: '<p>Some initial content</p>',
      content4: '<p>Some initial content</p>',
      content5: '<p>Some initial content</p>',
      customToolbar: [
            ['bold', 'italic', 'underline'],
            [{ 'list': 'ordered'}, { 'list': 'bullet' }],
            ['image', 'code-block']
      ],
    }
  },  
    methods: {
            formSubmit(e) {
                e.preventDefault();
                let currentObj = this;
                //let Delta = this.$refs.qc.$el.querySelector('.ql-editor').innerHTML;
                //let Delta = this.$refs.qc.$el.querySelector('.ql-editor').innerHTML;

                // this.$refs.quillEditorA.quill
                this.axios.post('http://localhost:62940/api/Questions', {
                    "situationId": 1,
                    "scenarioId": 1,
                    "name": " ",
                    "summary": {
                      "delta": [
                        {  } //quill contents
                      ]
                    },
                    "config": " ",
                    "statements": [
                      {
                        "statementId": 1,
                        "situationId": 1,
                        "name": " ",//name empty
                        "expression": {
                          "delta": [
                            {  }//quill config
                          ]
                        },
                        "truth": false, //set false
                        "explanation": " ",//empty
                        "config": " "
                      }
                    ]
                  }
                )
                .then(function (response) {
                    currentObj.output = response.data;
                    console.log(data);
                })
                .catch(function (error) {
                    currentObj.output = error;
                });
            }
        }
});
</script>


