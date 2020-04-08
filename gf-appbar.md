---
Descrição: >-
  GFAppbar é uma barra de ação superior, que fornece um espaço dedicado com recursos visuais estrutural e elementos interativos.
---

# GF Appbar

![GF App Bar](https://ik.imagekit.io/ionicfirebaseapp/docs/tr:dpr-auto,tr:w-auto/Appbar_-3bDD0z8f.png)




Uma barra de aplicativos consiste em uma barra de ferramentas e potencialmente em outros widgets, como um GFTabBar e  FlexibleSpaceBar. A GFAppBar exibe os widgets, iniciais, título e ações da barra de ferramentas acima. 

### Uso

O código simples de um GFAppbar básico é como mostrado abaixo.

```dart
import 'package:getflutter/getflutter.dart';

GFAppBar(
  leading:  GFIconButton(
    icon: Icon(
      Icons.message,
      color: Colors.white,
    ),
    onPressed: () {},
    type: GFButtonType.transparent,
  ),
  title: Text("GF Appbar"),
  actions: <Widget>[
    GFIconButton(
      icon: Icon(
        Icons.favorite,
        color: Colors.white,
      ),
      onPressed: () {},
      type: GFButtonType.transparent,
    ),
  ],
),
```

### GFAppbar com SearchBar

![App Bar with Search](.gitbook/assets/appbar-3.png)

If searchBar is true, it displays search bar textfield in the title space of the appbar with leading, trailing options. 

```dart
import 'package:getflutter/getflutter.dart';

GFAppBar(
  leading:  GFIconButton(
    icon: Icon(
      Icons.message,
      color: Colors.white,
    ),
    onPressed: () {},
    type: GFButtonType.transparent,
  ),
  searchBar: true,
  title: Text("GF Appbar"),
  actions: <Widget>[
    GFIconButton(
      icon: Icon(
        Icons.favorite,
        color: Colors.white,
      ),
      onPressed: () {},
      type: GFButtonType.transparent,
    ),
  ],
),
```

### GFAppbar com Tabs Segmentadas

**Tabs** **Segmentadas** também pode ser usado dentro do **Appbar**. no  **title** campo da Appbar apenas defina o código da guia Segmentado e o trabalho será concluído. O código abaixo mostra uma guia segmentada simples dentro da Appbar

```dart
import 'package:getflutter/getflutter.dart';

TabController tabController;
  @override
  void initState() {
    super.initState();
    tabController = TabController(length: 3, vsync: this);
  }

  @override
  void dispose() {
    tabController.dispose();
    super.dispose();
  }
  
  return Scaffold(
      appBar: GFAppBar(
        backgroundColor: GFColors.getGFColor(GFColor.dark),
        title:   GFSegmentTabs(
          tabController: tabController,
          tabBarColor: GFColors.getGFColor(GFColor.light),
          labelColor: GFColors.getGFColor(GFColor.white),
          unselectedLabelColor: GFColors.getGFColor(GFColor.dark),
          indicator: BoxDecoration(
            color: GFColors.getGFColor(GFColor.dark),
          ),
          indicatorPadding: EdgeInsets.all(8.0),
          indicatorWeight: 2.0,
          border: Border.all(color: Colors.white, width: 1.0),
              initialIndex: 0,
              length: 3,
              tabs: <Widget>[
                Text(
                  "Tab1",
                ),
                Text(
                  "Tab2",
                ),
                Text(
                  "Tab3",
                ),
              ],
            ),
          ),
 body: GFTabBarView(controller: tabController, children: <Widget>[
   Center(
     child: Text('Tab 1'),
   ),
   Center(
     child: Text('Tab 2'),
   ),
   Center(
     child: Text('Tab 3'),
   ),
 ]),
);
```

A aparência da **SearchBar do GFAppbar** pode ser personalizada usando as propriedades do GFAppbar.

### Propriedades Personalizadas

| Nome | Descrição |
| :--- | :--- |
| **searchBar** | Se verdadeiro, exibe a barra de pesquisa no espaço do título |
| **searchHintText** | É necessário texto para exibir o texto da dica da barra de pesquisa |
| **searchHintStyle** | Ele estiliza o \[searchHintText\] |
| **searchTextStyle** | Ele estiliza o texto de pesquisa |
| **searchBarColorTheme** | Define o tema da cor dos ícones da barra de pesquisa |
| **searchController** | Controla o texto que está sendo editado. Se nulo, esse widget criará seu próprio \[TextEditingController\] |
| **onChanged** | Chamado quando o usuário inicia uma alteração no valor do TextField: quando ele inseriu ou excluiu o texto |
| **onSubmitted** | Chamado quando o usuário indica que terminou de editar o texto no campo. |
| **onTap** | Chamado para cada toque distinto, exceto para cada segundo toque de um toque duplo. Se o campo de texto for criado com false ativado, os toques não serão reconhecidos. |

A aparência do **GFAppbar** pode ser personalizada usando as propriedades do **GFAppbar**.

### Propriedades Personalizadas
```dart
<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>leading</b>
      </td>
      <td style="text-align:left">A widget to display before the [title]</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>automaticallyImplyLeading</b>
      </td>
      <td style="text-align:left">Controls whether we should try to imply the leading widget if null. If
        true and [leading] is null, automatically try to deduce what the leading
        widget should be. If false and [leading] is null, leading space is given
        to [title]. If leading widget is not null, this parameter has no effect.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>title</b>
      </td>
      <td style="text-align:left">The primary widget displayed in the app bar. Typically a [Text] widget
        containing a description of the current contents of the app.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>actions</b>
      </td>
      <td style="text-align:left">Widgets to display after the [title] widget. Typically these widgets are
        [IconButton]s representing common operations. For less common operations,
        consider using a [PopupMenuButton] as the last action.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>flexibleSpace</b>
      </td>
      <td style="text-align:left">
        <p>This widget is stacked behind the toolbar and the tab bar. It&apos;s height
          will</p>
        <p>be the same as the app bar&apos;s overall height.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>bottom</b>
      </td>
      <td style="text-align:left">This widget appears across the bottom of the app bar. Typically a [TabBar].
        Only widgets that implement [PreferredSizeWidget] can be used at the bottom
        of an app bar.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>elevation</b>
      </td>
      <td style="text-align:left">The z-coordinate at which to place this app bar relative to its parent.
        This controls the size of the shadow below the app bar. The value is non-negative.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>shape</b>
      </td>
      <td style="text-align:left">The material&apos;s shape as well its shadow. A shadow is only displayed
        if the [elevation] is greater than zero.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>backgroundColor</b>
      </td>
      <td style="text-align:left">The color to change background color of the app bar&apos;s material.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>brightness</b>
      </td>
      <td style="text-align:left">The brightness of the app bar&apos;s material. Typically this is set along
        with [backgroundColor], [iconTheme], [textTheme].</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iconTheme</b>
      </td>
      <td style="text-align:left">The color, opacity, and size to use for app bar icons. Typically this
        is set along with [backgroundColor], [brightness], [textTheme].</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>actionsIconTheme</b>
      </td>
      <td style="text-align:left">The color, opacity, and size to use for the icons that appear in the appbar&apos;s
        [actions]. This should only be used when the [actions] should be themed
        differently than the icon that appears in the app bar&apos;s [leading]
        widget.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>textTheme</b>
      </td>
      <td style="text-align:left">The typographic styles to use for text in the app bar. Typically this
        is set along with [brightness] [backgroundColor], [iconTheme].</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>primary</b>
      </td>
      <td style="text-align:left">Whether this app bar is being displayed at the top of the screen. If true,
        the app bar&apos;s toolbar elements and [bottom] widget will be padded
        on top by the height of the system status bar. The layout of the [flexibleSpace]
        is not affected by the [primary] property.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>centerTitle</b>
      </td>
      <td style="text-align:left">Whether the title should be centered. Defaults to being adapted to the
        current [TargetPlatform].</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>titleSpacing</b>
      </td>
      <td style="text-align:left">
        <p>The spacing around [title] content on the horizontal axis. This spacing
          is applied even if there is no [leading] content or [actions]. If you want</p>
        <p>[title] to take all the space available, set this value to 0.0.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>toolbarOpacity</b>
      </td>
      <td style="text-align:left">How opaque the toolbar part of the app bar is. A value of 1.0 is fully
        opaque, and a value of 0.0 is fully transparent.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>bottomOpacity</b>
      </td>
      <td style="text-align:left">How opaque the bottom part of the app bar is. A value of 1.0 is fully
        opaque, and a value of 0.0 is fully transparent.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>preferredSize</b>
      </td>
      <td style="text-align:left">A size whose height is the sum of [kToolbarHeight] and the [bottom] widget&apos;s
        preferred height. [Scaffold] uses this size to set its app bar&apos;s height.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>searchBar</b>
      </td>
      <td style="text-align:left">If true, displays search bar in the title space</td>
    </tr>
  </tbody>
</table>
```