#ag-Grid
[ag Grid](https://www.ag-grid.com/)

## 基本使用
* 引入文件
```html
<link rel="stylesheet" href="lib/ag-grid/dist/styles/ag-grid.css">
<link rel="stylesheet" href="lib/ag-grid/dist/styles/theme-fresh.css">
<script type="text/javascript" src="lib/ag-grid/dist/ag-grid.min.js"></script>
```
* 加载module
```js
agGrid.initialiseAgGridWithAngular1(angular);
angular.module('app.core', ['ngSanitize', 'ui.bootstrap', 'ngAnimate', "agGrid"]);
```
* Html Template
```js
<div ag-grid="gridOptions" class="ag-fresh" style="height:200px;"></div>
```
* Js Controller
```js
angular.module('app.core').controller('HomeCtrl', ['$scope', function ($scope) {
    var rowData = [
        {make: "Toyota", model: "Celica", image: "images/002.png"},
        {make: "Ford", model: "Mondeo", image: "images/002.png"},
        {make: "Porsche", model: "Boxter", image: "images/002.png"}
    ];
    var columnDefs = [
        {headerName: "Make", field: "make"},
        {headerName: "Model", field: "model"},
        {
            headerName: "image",
            field: "image",
            template: '<div><img src="{{data.image}}"  height="100"></div>'
        }
    ];
    $scope.gridOptions = {
        angularCompileRows: true,
        rowHeight: 45,
        columnDefs: columnDefs,
        rowData: rowData,
        enableColResize: true
    };
}
```

## 使用
### 刷新数据和格式
```js
// 使用setXXX来刷新数据
$scope.gridOptions.api.setColumnDefs(columnDefs);
$scope.gridOptions.api.setRowData(rowData2);
```
 