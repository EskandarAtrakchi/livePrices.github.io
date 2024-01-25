# livePrices.github.io

# My Notes Web Application

This repository contains the source code for a simple web application called "My Notes."

## Table of Contents

- [Introduction](#introduction)
- [HTML Structure](#html-structure)
- [CSS Styling](#css-styling)
- [JavaScript Logic](#javascript-logic)

## Introduction

The "My Notes" web application allows users to create and view notes in an interactive interface.

## HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags and title -->
    <!-- External stylesheet, font-awesome, and JavaScript file links -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link rel="website icon" href="https://moonbeam.network/wp-content/uploads/2020/10/rotating-ethereum-logo.gif">
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
    <title>My Notes</title>
</head>
<body>
    <!-- Heading and iframe to display notes -->
    <h1>My Notes</h1>
    <iframe width="100%" height="1400" src="Notes.html" title="Notes by Eskandar Atrakchi" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</body>
</html>
```

## JavaScript Logic starts here with additional comments to know hw it works


```// JavaScript logic for My Notes web application

// Function to search for text within the document
function searchText() {
    const searchText = document.getElementById("searchInput").value;
    const bodyText = document.body.textContent;

    if (bodyText.includes(searchText)) {
        const startIndex = bodyText.indexOf(searchText);
        const endIndex = startIndex + searchText.length;
        const matchingText = bodyText.substring(startIndex, endIndex);

        document.getElementById("searchResults").innerHTML = matchingText;
    } else {
        document.getElementById("searchResults").innerHTML = 'Does not exist! Try something different!';
    }
}

// Crypto widget initialization for retrieving and displaying cryptocurrency prices
!function(){
    var e=document.getElementsByTagName("script"),
    t=e[e.length-1],
    n=document.createElement("script");

    function r(){
        var e=crCryptocoinPriceWidget.init({
            // Configuration for the crypto widget
            base:"USD,EUR,CNY,GBP",
            items:"BTC,ETH,PRQ,LTC,SOL,XMR,DASH,XRP,XLM,NANO,GLQ,ADA,TRX,DOT,ATOM,VET,NEAR,INJ,TWT,LINK,MATIC,NTRN",
            backgroundColor:"343A40",
            streaming:"1",
            striped:"1",
            rounded:"1",
            boxShadow:"1",
            border:"1"
        });
        t.parentNode.insertBefore(e,t)
    }

    n.src="https://co-in.io/widget/pricelist.js?items=BTC%2CETH%2CLTC%2CXMR%2CDASH%2CXRP%2CXLM%2CNANO",
    n.async=!0,
    n.readyState?n.onreadystatechange=function(){
        "loaded"!=n.readyState&&"complete"!=n.readyState||(n.onreadystatechange=null,r())
    }:n.onload=function(){r()},
    t.parentNode.insertBefore(n,null)
}();
</script>
</body>
</html>


```