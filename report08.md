---
# Front matter
lang: ru-RU  
title: "Отчёт по лабораторной работе №8"  
subtitle: "дисциплина: Математическое моделирование"  
author: "Рыбалко Элина Павловна"  

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
  - spelling=modern
  - babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

  Рассмотреть модель конкуренции двух фирм для двух случаев (без учёта и с учётом социально-психологического фактора) и их построение с помощью языка программирования Modelica.  

## Объект исследования

  Модель конкуренции двух фирм.

## Предмет исследования

  Алгоритм построения графика конкуренции двух фирм.

# Теоретическое введение

  Для построения модели конкуренции хотя бы двух фирм необходимо рассмотреть модель одной фирмы. Вначале рассмотрим модель фирмы, производящей продукт долговременного пользования, когда цена его определяется балансом спроса и предложения. Примем, что этот продукт занимает определенную нишу рынка и конкуренты в ней отсутствуют. Обозначим: N – число потребителей производимого продукта. S – доходы потребителей данного продукта. Считаем, что доходы всех потребителей одинаковы. Это предположение справедливо, если речь идет об одной рыночной нише, т.е. производимый продукт ориентирован на определенный слой населения. M – оборотные средства предприятия $\tau$ – длительность производственного цикла $\rho$ – рыночная цена товара  $\widetilde{\rho}$ – себестоимость продукта, то есть переменные издержки на производство единицы продукции. $\sigma$ – доля оборотных средств, идущая на покрытие переменных издержек. k – постоянные издержки, которые не зависят от количества выпускаемой продукции. Q(S/p) – функция спроса, зависящая от отношения дохода S к цене p. Она равна количеству продукта, потребляемого одним потребителем в единицу времени. Функцию спроса товаров долговременного использования часто представляют в простейшей форме (см. рис. -@fig:004).

  ![Уравнения](image/4.png){ #fig:004 width=70% }

  где q – максимальная потребность одного человека в продукте в единицу времени. Эта функция падает с ростом цены и при p = pcr (критическая стоимость продукта) потребители отказываются от приобретения товара. Величина pcr = Sq/k. Параметр k – мера эластичности функции спроса по цене. Таким образом, функция спроса в форме (1) является пороговой (то есть, Q(S/p) = 0 при p ≥ pcr) и обладает свойствами насыщения. Уравнения динамики оборотных средств можно записать в виде  (см. рис. -@fig:005).

  ![Уравнения](image/5.png){ #fig:005 width=70% }

  Уравнение для рыночной цены p представим в виде  (см. рис. -@fig:006).

  ![Уравнения](image/6.png){ #fig:006 width=70% }

  Первый член соответствует количеству поставляемого на рынок товара (то есть, предложению), а второй член – спросу. Параметр $\gamma$ зависит от скорости оборота товаров на рынке. Как правило, время торгового оборота существенно меньше времени производственного цикла $\tau$. При заданном M уравнение (3) описывает быстрое стремление цены к равновесному значению цены, которое устойчиво. В этом случае уравнение (3) можно заменить алгебраическим соотношением  (см. рис. -@fig:007).

  ![Уравнения](image/7.png){ #fig:007 width=70% }

  Из этого следует, что равновесное значение цены p равно (см. рис. -@fig:008).

  ![Уравнения](image/8.png){ #fig:008 width=70% }
  
  Уравнение с учетом приобретает вид  (см. рис. -@fig:009).

  ![Уравнения](image/9.png){ #fig:009 width=70% }

  Уравнение имеет два стационарных решения, соответствующих условию dM/dt = 0  (см. рис. -@fig:010, -@fig:011):

  ![Уравнения](image/10.png){ #fig:0010 width=70% }

  где

  ![Уравнения](image/11.png){ #fig:0011 width=70% }

  Из (7) следует, что при больших постоянных издержках (в случае a 2 < 4b) стационарных состояний нет. Это означает, что в этих условиях фирма не может функционировать стабильно, то есть, терпит банкротство. Однако, как правило, постоянные затраты малы по сравнению с переменными (то есть, b << a 2 ) и играют роль, только в случае, когда оборотные средства малы. При b << a стационарные (см. рис. -@fig:012).

  ![Уравнения](image/12.png){ #fig:0012 width=70% }

  Первое состояние $M_+$ устойчиво и соответствует стабильному функционированию предприятия. Второе состояние $M_-$ неустойчиво, так, что при $M_+ < M_-$ оборотные средства падают (dM/dt < 0), то есть, фирма идет к банкротству. По смыслу $M_-$ соответствует начальному капиталу, необходимому для входа в рынок. В обсуждаемой модели параметр $\sigma$ всюду входит в сочетании с $\tau$. Это значит, что уменьшение доли оборотных средств, вкладываемых в производство, эквивалентно удлинению производственного цикла. Поэтому мы в дальнейшем положим: $\sigma$ = 1, а параметр $\tau$ будем считать временем цикла, с учётом сказанного.  [[1]](#список-литературы) 

# Задание

  1. Придумайте свой пример двух конкурирующих фирм с идентичным  товаром. Задайте начальные значения и известные составляющие. Постройте графики изменения объемов оборотных средств каждой фирмы. Рассмотрите два случая.
  2. Проанализируйте полученные результаты.
  3. Найдите стационарное состояние системы для первого случая.


# Выполнение лабораторной работы

## 1. Постановка задачи

**[Вариант 22]**

   Рассмотрим две фирмы, производящие взаимозаменяемые товары одинакового качества и находящиеся в одной рыночной нише. Считаем, что в рамках нашей модели конкурентная борьба ведётся только рыночными методами. То есть, конкуренты могут влиять на противника путем изменения параметров своего производства: себестоимость, время цикла, но не могут прямо вмешиваться в ситуацию на рынке («назначать» цену или влиять на потребителей каким-либо иным способом.) Будем считать, что постоянные издержки пренебрежимо малы, и в модели учитывать не будем. В этом случае динамика изменения объемов продаж фирмы 1 и фирмы 2 описывается следующей системой уравнений (см. рис. -@fig:001).

  ![ Уравнения](image/1.png){ #fig:001 width=70% }
    
  Рассмотрим модель, когда, помимо экономического фактора влияния (изменение себестоимости, производственного цикла, использование кредита и т.п.), используются еще и социально-психологические факторы – формирование общественного предпочтения одного товара другому, не зависимо от их качества и цены. В этом случае взаимодействие двух фирм будет зависеть друг от друга, соответственно коэффициент перед M M1 2 будет отличаться. Пусть в рамках рассматриваемой модели динамика изменения объемов продаж фирмы 1 и фирмы 2 описывается следующей системой уравнений (см. рис. -@fig:002).

  ![Уравнения](image/2.png){ #fig:002 width=70% }

  Для обоих случаев рассмотрим задачу со следующими начальными условиями и параметрами (см. рис. -@fig:003).

  ![Уравнения](image/3.png){ #fig:003 width=70% }

  1. Постройте графики изменения оборотных средств фирмы 1 и фирмы 2 без  учета постоянных издержек и с веденной нормировкой для случая 1.
  2. Постройте графики изменения оборотных средств фирмы 1 и фирмы 2 без  учета постоянных издержек и с веденной нормировкой для случая 2.


## 2. Построение графиков 

### 2.1. Листинги программ в OpenModelica

  1. Написала программу на Modelica:

  Программа:

  ```
    model lab08_1
    parameter Real p_cr = 44;
    parameter Real tau1 = 26;
    parameter Real p1 = 11;
    parameter Real tau2 = 21;
    parameter Real p2 = 8.7;
    parameter Real N = 77;
    parameter Real q = 1;

    parameter Real a1=p_cr/(tau1*tau1*p1*p1*N*q);
    parameter Real a2=p_cr/(tau2*tau2*p2*p2*N*q);
    parameter Real b=p_cr/(tau1*tau1*tau2*tau2*p1*p1*p2*p2*N*q);
    parameter Real c1=(p_cr-p1)/(tau1*p1);
    parameter Real c2=(p_cr-p2)/(tau2*p2);

    parameter Real M0_1=7.1;
    parameter Real M0_2=8.1;
    Real M1(start=M0_1);
    Real M2(start=M0_2);

    equation
    der(M1)=M1-(b/c1)*M1*M2-(a1/c1)*M1*M1;
    der(M2)=(c2/c1)*M2-(b/c1)*M1*M2-(a2/c1)*M2*M2;
    // der(M1) = M1-(b/c1+0.0013)*M1*M2-(a1/c1)*M1*M1;
    //der(M2) = (c2/c1)*M2-(b/c1)*M1*M2-(a2/c1)*M2*M2;
    end lab08_1;
  ```


### 2.2. Полученный график  

  После запуска кода программы получили следующие графики для первого и второго случая соответственно  (см. рис. -@fig:013 и -@fig:014).

  ![График изменения оборотных средств фирм в случае 1](image/13.png){ #fig:013} 

  ![График изменения оборотных средств фирмы M1 в случае 2](image/14.png){ #fig:014}

  ![График изменения оборотных средств фирм в случае 2](image/15.png){ #fig:015}


### 2.4. Поиск стационарного состояния: 

  Исходя из рис. -@fig:010 и -@fig:011 найдём стационарные состояния для 1 случая. 
  Первая фирма:

  a ≈ 16516,5
  b ≈ 143143
  >M1 ≈ 16507,8
  M2 ≈ 8,67

  Вторая фирма:
  a ≈ 11254,32
  b ≈ 58413,76
  >M1 ≈ 11249,13 
  M2 ≈ 5,2

  ![Стационарное состояние фирмы 1](image/16.png){ #fig:016} 

  ![Стационарное состояние фирмы 2](image/17.png){ #fig:017}

  Исходя из построенных графиков (см. рис. -@fig:016 и -@fig:017) убедимся в наших примерных вычислениях. Для первой фирмы стационарное значение ≈ 16516,2 млн.единиц. Для второй фирмы стационарное значение ≈ 11286,1 млн.единиц. 

### 2.5. Анализ результатов:

  Из рис. -@fig:013 видно, что рост оборотных средств предприятий идет независимо друг от друга.
  Каждая фирма достигает свое максимальное значение обёма продаж примерно в 16516,2 и 11286,1 млн единиц, соответственно, и остаётся на рынке с этим значением, то есть каждая фирма захватывает свою часть рынка потребителей, которая не изменяется. 

  Из рис. -@fig:014 и -@fig:015 видно, что первая фирма, несмотря на начальный рост, достигнув своего  максимального объема продаж примерно в 60 млн.единиц, начитает нести убытки и, в итоге, терпит банкротство. Динамика роста объёмов оборотных средств второй фирмы остается без изменения: достигнув максимального значения порядка 11 млрд. единиц, остаётся на этом уровне.

# Вывод

  Рассмотрели модель конкуренцтт двух фирм для двух случаев (без учёта и с учётом социально-психологического фактора) и их построение с помощью языка программирования Modelica. 

# Список литературы {.unnumbered}

1. [Конкуренция двух фирм](https://megaobuchalka.ru/3/24672.html)
2. [Руководство по формуле Cmd Markdown](https://russianblogs.com/article/26051452570/)
3. [Математическое моделирование при решении задач](https://urok.1sept.ru/articles/609795)
4. [С.В. Каштаева, Математическое моделирование / Учебное пособие](http://pgsha.ru:8008/books/study/%CA%E0%F8%F2%E0%E5%E2%E0%20%D1.%20%C2.%20%CC%E0%F2%E5%EC%E0%F2%E8%F7%E5%F1%EA%EE%E5%20%EC%EE%E4%E5%EB%E8%F0%EE%E2%E0%ED%E8%E5..pdf)
5. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637)