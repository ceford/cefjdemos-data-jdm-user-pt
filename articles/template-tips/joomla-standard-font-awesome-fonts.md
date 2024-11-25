<!-- Filename: J4.x:Joomla_Standard_Font_Awesome_Fonts / Display title: Fontes do Font Awesome  -->

## Como Usar

O CMS Joomla! vem com seu próprio conjunto personalizado de fontes Font Awesome. Essas fontes de ícones estão disponíveis por padrão para uso nos templates *Cassiopeia* e *Atum*.

Fontes de ícones mapeadas em `/media/system/scss/_icomoon.scss` podem ser chamadas com uma tag `name-of-icon">` e um {espaço} `</span>`. Exemplo:

```html
<span class="icon-joomla"> </span>
```

Irá mostrar o ícone do Joomla!: <span class="icon-joomla">&nbsp;</span>

Fontes de ícones que não estão mapeadas podem ser chamadas com uma tag `<span class="far fa-name-of-icon">` e um {espaço} `</span>`. Exemplo:

```php
<i class="fa fa-adjust"></i>
```

Irá mostrar um ícone de ajuste: <i class="fa fa-adjust"></i>

## Tamanho da Fonte

Como os ícones são fontes, você pode controlar o tamanho deles com uma classe adicional ou uma declaração style=. Claro que você terá que definir a classe no seu arquivo de folha de estilo .css ou .less.

```html
<span class="icon-joomla large-icon"> </span>
<span class="icon-joomla" style="font-size:24px;"> </span>
```

Aqui está o ícone do Joomla! redimensionado: <span class="icon-joomla" style="font-size:24px;">&nbsp;</span>

