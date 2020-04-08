---
Descrição: >-
  GF Alert é um widget simples que é usado para mostrar algumas informações e aguardar
  a ação do usuário.
---

# GF Alert

![Alert](https://ik.imagekit.io/ionicfirebaseapp/tr:dpr-auto,tr:w-auto/docs/Alerts_2x_BDFQKkxzq.png)



### 

### Uso

**GFAlert** deve estar dentro de um **GFFloating** Widget o **child** do **GFFloatingWidget** leva **GFAlert** toma como um argumento o  **body** leva qualquer tipo de widgets. O código de alerta é como mostrado abaixo.. 

```dart
import 'package:getflutter/getflutter.dart';
 
 return Scaffold(
   body:GFFloatingWidget(
     child:GFAlert(
              title: 'Welcome !',
              content: 'Get Flutter is one of the largest Flutter open-source UI library for mobile or web apps with  1000+ pre-built reusable widgets.',
              bottombar: Row(
                 mainAxisAlignment: MainAxisAlignment.end,
                 children: <Widget>[
                    GFButton(
                      onPressed: (){
                      setState(() {
                        showalert=false;
                    });
                  },
                    shape: GFButtonShape.pills,
                    icon: Icon(Icons.keyboard_arrow_right, color: GFColors.getGFColor(GFColor.white),),
                    position: GFPosition.end,
                    text: 'Learn More',)
                ],
              ),
            )
   body:Text('body or any kind of widget here..')
 )
)
```

### Alerta com vários Buttons

![Alert with Multiple Buttons](.gitbook/assets/basic-alert-2x.png)

O alerta pode ter dois ou mais **Buttons** para chamada de ação no **bottombar** do widget de alerta. O código abaixo mostra os vários botões.

```dart
import 'package:getflutter/getflutter.dart';
 
 return Scaffold(
   body:GFFloatingWidget(
     child:GFAlert(
              title: 'Welcome !',
              content: 'Get Flutter is one of the largest Flutter open-source UI library for mobile or web apps with  1000+ pre-built reusable widgets.',
              bottombar: Row(
                 mainAxisAlignment: MainAxisAlignment.end,
                 children: <Widget>[
                  GFButton(
                      onPressed: (){
                      setState(() {
                        showalert=false;
                    });
                  },
                    shape: GFButtonShape.pills,
                     child: Text('Skip',style: TextStyle(color: Colors.black)),
                   SizedBox(
                    width:5
                    ),
                    GFButton(
                      onPressed: (){
                      setState(() {
                        showalert=false;
                    });
                  },
                    shape: GFButtonShape.pills,
                    icon: Icon(Icons.keyboard_arrow_right, color: GFColors.getGFColor(GFColor.white),),
                    position: GFPosition.end,
                    text: 'Learn More',)
                ],
              ),
            )
   body:Text('body or any kind of widget here..')
 )
)
```

### Tipos de Alertas 


Existem os tipos de alertas, ou seja, `basic` , `rounded` and `fullWidth` . 
O alerta padrão é um alerta básico. O código abaixo mostra o  **rounded** alerta. Para o **fullWidth** trocando pelo alerta **rounded** com **fullWidth**

```dart
import 'package:getflutter/getflutter.dart';
 
 return Scaffold(
   body:GFFloatingWidget(
     child:GFAlert(
              title: 'Welcome !',
              content: 'Get Flutter is one of the largest Flutter open-source UI library for mobile or web apps with  1000+ pre-built reusable widgets.',
              type: GFAlertType.rounded,
              bottombar: Row(
                 mainAxisAlignment: MainAxisAlignment.end,
                 children: <Widget>[
                  GFButton(
                      onPressed: (){
                      setState(() {
                        showalert=false;
                    });
                  },
                    shape: GFButtonShape.pills,
                     child: Text('Skip',style: TextStyle(color: Colors.black)),
                   SizedBox(
                    width:5
                    ),
                    GFButton(
                      onPressed: (){
                      setState(() {
                        showalert=false;
                    });
                  },
                    shape: GFButtonShape.pills,
                    icon: Icon(Icons.keyboard_arrow_right, color: GFColors.getGFColor(GFColor.white),),
                    position: GFPosition.end,
                    text: 'Learn More',)
                ],
              ),
            )
   body:Text('body or any kind of widget here..')
 )
)
```

### Posicionamento do Alerta


Os alertas podem ser posicionados adequadamente dentro do **GFFloating** Widget.O posicionamento requer dois parâmetros, ou seja, **horizontalPosition** e **verticalPosition**.
O uso destes é mostrado abaixo.

```dart
import 'package:getflutter/getflutter.dart';

body:GFFloatingWidget(
    horizontalPosition:40.0,
    verticalPosition:20.0,
    child:GFAlert(
    title: 'Welcome!',
  ),
 body:Text('body or any kind of widget here..')
)
```



### Propriedades Personalizadas

|  |  |
| :--- | :--- |
| **child** | **child** do tipo \[Widget\] que é alternativa ao  **title**. **title** terá prioridade sobre **child** |
| **contentChild** | **contentchild** do tipo \[Widget\] que é alternativa a **content**. **content** terá prioridade sobre **contentchild** |
| **titleTextStyle** | muda o estilo do **title**  não para o **child** |
| **backgroundColor** | usado para alterar o backgroundColor do GFAlert |
| **contentTextStyle** | muda o estilo do **content**  não para o **contentChild** |
| **width** | usado para controlar a largura do**Alert** |
| **alignment** | usado para alinhar o **title ou content** para a posição desejada  |

