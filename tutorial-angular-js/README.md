tutorial-angular-js
===================

Código utilizado no Tutorial AngularJS


DIRETIVAS

ng-app
definir o nome da aplicação que ele deve visualizar, o nome
do modulo q ele deve buscar, significado q vai ser a inicia
lização do meu módulo


ng-controller
define um controller para determinado trecho de codigo


ng-bind
associa

é o mesmo q:
Vc clicou {{contador}} no botao
Vc clicou <span ng-bind="contador"></span> vezes no botao

ng-model
"amarra" um campo input a uma propriedade do controller
pega os dados informados pelo usuario
<input type="text" ng-model="estado" placeholder="Digite um estado" />
tudo que for digitado dentro do input vai ser refletido dentro do meu controller

ng-repeat (for)
<ul class="list-group">
      <!-- diretiva ng-repeat -->
      <li class="list-group-item" ng-repeat="state in states">{{state.name}} - {{state.capital}}</li>
    </ul>

NO CONTROLLER FICA ASSIM:
$scope.states = [
		{name:'Minas Gerais', capital: 'Belo Horizonte'},
		{name:'São Paulo', capital: 'São Paulo'},
		{name:'Paraíba', capital: 'João Pessoa'}
];

ng-show
Deixa visivel um elemento de acordo com uma expressao
booleana
HTML:
<p>
      <!-- diretiva ng-model -->
      Gostei
      <input type="checkbox" ng-model="gostei" />
      <!-- diretiva ng-show -->
      <span class="glyphicon glyphicon-thumbs-up" ng-show="gostei"></span>
</p>
CONTROLLER:
$scope.gostei = false;

ng-hide
se determina ele true, esconde o elemento


ng-click
eu defino ql acao sera executado qndo eu clicar



--------------------
Lógica deve ficar nas views

os models devem carregar os dados

e as views preparam para visualizar


----------------------

Filtros e os principais q ja vem com angular:

============ html ===================

<p>Filtrar: <input type="text" ng-model="filtro" /></p>

    <ul class="list-group">
      <!-- diretiva ng-repeat -->
      <li class="list-group-item" ng-repeat="state in states | orderBy:'name' | filter:filtro">
      {{state.name | uppercase}} - {{state.capital | lowercase}} - renda per capita: {{state.renda | currency:'R$'}}
      </li>
    </ul>

==============fim html filtros=========




1. currency

transforma um numero em formato monetario


2. date
formata como data 
data No html:
<p>Data: {{data | date:'dd/MM/yyyy'}}</p>

e no controller:
  $scope.data = new Date();

3. orderBy
<li class="list-group-item" ng-repeat="state in states | orderBy:'name' | filter:filtro">
ordenar crescente ou decrescente q seria -orderBy:'name'

4. filter

5. json
é mais usado para debugar
 <p>Letras (json): {{states[0].renda| json }}</p>
    <p>Letras (json): {{states[0].capital | json }}</p>
    <p>Letras (json): {{states | json }}</p>


6. lowercase
passa todos os caracteres para letra minuscula
7. uppercase

8. limitTo



------------------------