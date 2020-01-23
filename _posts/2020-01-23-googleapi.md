---
title: "Projeto com Data Science e Google Scripts para gera��o de valor"
date: 2018-01-28
tags: [Google API, BI, data science, javascript]
header:
  image: 
excerpt: "Data Science, Google API, JavaScript"
mathjax: "true"
---

# Gera��o de insights com Data Science e automa��o de rotinas com google scripts


Esse projeto foi feito em partes:
1- Atrav�s das ordens de mercado dos traders que era exportado da plataforma de opera��es para um arquivo .csv, um script calculava o resultado mensal acumulado dos alunos, com atualiza��o di�ria autom�tica.
2- V�rias atividades eram feitas pelos traders e registradas em planilhas no google drive, um outro script foi usado para ler as planilhas e calcular notas em cada categoria para os traders.
3- Foi poss�vel relacionar a efici�ncia das atividades com o desempenho no mercado real e o resultado foi apresentado aos traders.
4- Um outro script era usado para ler todas as planilhas, gerar um relat�rio em PDF e enviar por email para os diretores semanalmente.

<img src="{{ site.url }}{{ site.baseurl }}/images/api/resultados.jpg" alt="linearly separable data">

<img src="{{ site.url }}{{ site.baseurl }}/images/api/evolucao.jpg" alt="linearly separable data">





Exemplo:
```javascript
     //verifica nota GD
  var GDfolder = DriveApp.getFolderById('XXXXXXXXXXXXXXXXX');
  sheetD.getRange(2, 9, sheetD.getLastRow()-1).setValue(0);
  var GDs = GDfolder.searchFiles("title contains 'xlsx'");
  while(GDs.hasNext()){
    var gd = GDs.next();
    var nome = gd.getName().substring(0,gd.getName().indexOf('.xlsx'));
    var row = searchByName(range,nome);
    if(row<=range.getValues().length){
      var conv = Drive.Files.insert('', gd.getBlob(), {convert: true});
      var data = SpreadsheetApp.openById(conv.id).getActiveSheet().getDataRange().getValues();
      var nota = data[d.getMonth()+1][1];
      range.getCell(row, 9).setValue(nota/10);
      Drive.Files.remove(conv.id);
    }    
  }
```
