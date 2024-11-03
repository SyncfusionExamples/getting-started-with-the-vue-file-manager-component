
<script setup>
  import { FileManagerComponent, NavigationPane, 
    Toolbar, DetailsView
   } from '@syncfusion/ej2-vue-filemanager';
   import { provide } from "vue";
  const filemanager = [DetailsView, NavigationPane, Toolbar];
  provide('filemanager', filemanager);
  
  const baseUrl = "https://ej2-aspcore-service.azurewebsites.net/";
  // Ajax settings for FileManager
  const ajaxSettings = {
    url: baseUrl + `api/FileManager/FileOperations`,
    downloadUrl: baseUrl + `api/FileManager/Download`,
    uploadUrl: baseUrl + `api/FileManager/Upload`,
    getImageUrl: baseUrl + `api/FileManager/GetImage`
  };
</script>
<template>
  <div className='container'>
    <FileManagerComponent
      :ajaxSettings="ajaxSettings"
    >
    </FileManagerComponent>
  </div>
</template>
<style>
  @import "../node_modules/@syncfusion/ej2-base/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-icons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-layouts/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-vue-filemanager/styles/material.css";
  .container{
    margin-top: 10%;
    height: 500px;
    width: 670px;
    margin-left: 22.5%;
  }
</style>
