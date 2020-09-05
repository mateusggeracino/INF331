## Lab05 - Web

### ALUNO
   >Mateus Gonçalves Geracino
<br><br>


## Tarefa 1

![imagem](imagens/tarefa1.png)

## Tarefa 2
Link codepen: [React 03 - Componente Barra](https://codepen.io/mateusggeracino/pen/ZEWaMBK)

**HTML**
~~~html
<div class="position">
  <div id="root"></div>
  <div id="text"></div>
  <div id="container-dinossaur"></div>
</div>
~~~

**JavaScript**
~~~javascript
class Barra extends React.Component {
  render() {
    let resultado = "";
    for (let b = 1; b <= this.props.tamanho; b++)
      resultado += "=";
    return resultado;
  }
}

const elemento = <div>
                   <h2>O dinossauro</h2>
                   <Barra tamanho="10"/>
                   <h2>pulou na lama.</h2>
                 </div>
ReactDOM.render(elemento, 
        document.getElementById("root"));

const dinossaur = <div>
                   <img id="comet" src="https://i.ibb.co/WFrNgd6/comet.png"></img>
                   <img id="dinossaur" onclick="killdinossaur()" src="https://cdn.dribbble.com/users/707812/screenshots/4621284/trex.gif"/>
                  </div>
      
ReactDOM.render(dinossaur, document.getElementById("container-dinossaur"))
      
var moveDiv = document.getElementById('comet');
window.onmousemove = function (e) {
    var x = e.pageX,
        y = e.pageY;
    moveDiv.style.top = (y + (-80)) + 'px';
    moveDiv.style.left = (x + 10) + 'px';
};

var i = 0;
var ref = setInterval(() => {  
  ReactDOM.render(<p>Correndo: {i} km</p>, document.getElementById('text'));
  i++;
  if (i == 9999) clearInterval(ref);
}, 400);
~~~
