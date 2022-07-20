---
title: Titel of this Paper
author: @phense
date: \today
documentclass: scrartcl
classoption: a4paper, 12pt, oneside, english
inputenc: utf8
geometry: top=2.5cm, bottom=2.5cm, left=3cm, right=2.5cm
indent: true
colorlinks: urlcolor=NavyBlue
header-includes: |
  \usepackage[english]{babel}
  \usepackage{amsmath, amsthm}
  \usepackage{fancyhdr}
  \usepackage{mathptmx}		%% Serif Font and Symbols %%
  \usepackage{titling}		%% make title variables available always %%
  %% delete the Title from Template %%
  \renewcommand\maketitle{} 
  %% redefine font for captions %%
  \setkomafont{sectioning}{\normalfont\bfseries \large}
  \setkomafont{captionlabel}{\normalfont\bfseries}
  \setkomafont{pageheadfoot}{\normalfont\itshape}
  \setkomafont{descriptionlabel}{\normalfont\bfseries}
  %% set header and footer %% 
  %% variables come from the titling package %%
  \lhead{\theauthor}\chead{\thetitle}\rhead{\thedate}
  \lfoot{}\cfoot{}\rfoot{\thepage}
  \pagestyle{fancy}
---



# Header L1

$$
\begin{align}
a &= \frac{abc + cde^2}{2\pi r^2} \label{eq1}
\end{align}
$$

$$
\begin{align}
b &= \int_1^\infty \lg \left( \frac{sin \pi}{2 e^{-i \pi}} \right) \label{eq3}
\end{align}
$$

# Header L1

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod  tempor incididunt ut labore et dolore magna aliqua. Eget gravida cum  sociis natoque penatibus et magnis dis parturient. Consequat semper  viverra nam libero justo. Natoque penatibus et magnis dis parturient.  Tristique senectus et netus et malesuada fames. Aliquet bibendum enim  facilisis gravida neque. Libero id faucibus nisl tincidunt eget nullam.  Volutpat maecenas volutpat blandit aliquam etiam erat. Sagittis orci a  scelerisque purus semper. Lacus luctus accumsan tortor posuere ac ut  consequat semper viverra. Aliquet sagittis id consectetur purus ut  faucibus pulvinar elementum integer.

Feugiat nisl pretium fusce id. Sit amet massa vitae tortor. Ut  faucibus pulvinar elementum integer enim neque. Duis at tellus at urna  condimentum. Sociis natoque penatibus et magnis dis parturient montes.  Vitae sapien pellentesque habitant morbi tristique. Augue lacus viverra  vitae congue eu consequat ac. Id diam maecenas ultricies mi eget mauris  pharetra et. Non pulvinar neque laoreet suspendisse interdum. Aliquet  bibendum enim facilisis gravida neque convallis a cras semper.

## Header L2

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod  tempor incididunt ut labore et dolore magna aliqua. Eget gravida cum  sociis natoque penatibus et magnis dis parturient. Consequat semper  viverra nam libero justo. Natoque penatibus et magnis dis parturient.  Tristique senectus et netus et malesuada fames. Aliquet bibendum enim  facilisis gravida neque. Libero id faucibus nisl tincidunt eget nullam.  Volutpat maecenas volutpat blandit aliquam etiam erat. Sagittis orci a  scelerisque purus semper. Lacus luctus accumsan tortor posuere ac ut  consequat semper viverra. Aliquet sagittis id consectetur purus ut  faucibus pulvinar elementum integer.

Feugiat nisl pretium fusce id. Sit amet massa vitae tortor. Ut  faucibus pulvinar elementum integer enim neque. Duis at tellus at urna  condimentum. Sociis natoque penatibus et magnis dis parturient montes.  Vitae sapien pellentesque habitant morbi tristique. Augue lacus viverra  vitae congue eu consequat ac. Id diam maecenas ultricies mi eget mauris  pharetra et. Non pulvinar neque laoreet suspendisse interdum. Aliquet  bibendum enim facilisis gravida neque convallis a cras semper.

## Header L2

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod  tempor incididunt ut labore et dolore magna aliqua. Eget gravida cum  sociis natoque penatibus et magnis dis parturient. Consequat semper  viverra nam libero justo. Natoque penatibus et magnis dis parturient.  Tristique senectus et netus et malesuada fames. Aliquet bibendum enim  facilisis gravida neque. Libero id faucibus nisl tincidunt eget nullam.  Volutpat maecenas volutpat blandit aliquam etiam erat. Sagittis orci a  scelerisque purus semper. Lacus luctus accumsan tortor posuere ac ut  consequat semper viverra. Aliquet sagittis id consectetur purus ut  faucibus pulvinar elementum integer.

Feugiat nisl pretium fusce id. Sit amet massa vitae tortor. Ut  faucibus pulvinar elementum integer enim neque. Duis at tellus at urna  condimentum. Sociis natoque penatibus et magnis dis parturient montes.  Vitae sapien pellentesque habitant morbi tristique. Augue lacus viverra  vitae congue eu consequat ac. Id diam maecenas ultricies mi eget mauris  pharetra et. Non pulvinar neque laoreet suspendisse interdum. Aliquet  bibendum enim facilisis gravida neque convallis a cras semper.
