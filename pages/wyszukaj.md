---
title: wyszukaj
permalink: /wyszukaj/
layout: page
comments: true
---


<main class="page-content" aria-label="Content"> 
<div class="archive-tags"> 
    <a id="startup-tag-item" class="tag-item" onclick="filter('startup'); return false;">startup</a>
    <a id="produkt-tag-item" class="tag-item" onclick="filter('produkt'); return false;">produkt</a>
    <a id="tech-tag-item" class="tag-item" onclick="filter('tech'); return false;">tech</a> 
    <a id="vc-tag-item" class="tag-item" onclick="filter('vc'); return false;">vc</a> 
    <a id="finanse-tag-item" class="tag-item" onclick="filter('finanse'); return false;">finanse</a> 
    <a id="insurtech-tag-item" class="tag-item" onclick="filter('insurtech'); return false;">insurtech</a> 
    <a id="fintech-tag-item" class="tag-item" onclick="filter('fintech'); return false;">fintech</a> 
    <a id="inne-tag-item" class="tag-item" onclick="filter('inne'); return false;">inne</a> 
    </div>
    <br> 
    <br> 
    <div class="search-article"> <label for="search-input" aria-hidden="true"> <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="rgba(128,128,128,0.8)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-search"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg> </label> <input type="search" id="search-input" placeholder="wyszukaj wpis" aria-label="wyszukaj"> </div>
        <ul id="search-results"></ul> 
    <br> 
    <br> 
    <br>
    <hr> 
    <br> 
    <center>
        wolisz zobaczyć wszystkie możliwe wpisy na raz? 
    <br>
        sprawdź 
        <a href="https://remigiuszswiatkowski.substack.com/archive">archiwum</a> 
    </center> 
        <script src="/assets/js/search.min.js"></script>
        <script> let tagsArray = []; const urlParams = new URLSearchParams(window.location.search); const pickedTag = urlParams.get('tag'); let searchInput = document.getElementById('search-input'); async function filter(tag) { setActiveTag(tag); var event = new Event("input", { bubbles: true, cancelable: true, }); searchInput.dispatchEvent(event); }; function sleep(ms) { return new Promise(resolve => setTimeout(resolve, ms)); } function setActiveTag(tag) { if(tagsArray.includes(tag)){ const indexofTag = tagsArray.indexOf(tag); document.getElementById(tag+'-tag-item').classList.remove('picked'); tagsArray.splice(indexofTag, 1); } else { document.getElementById(tag+'-tag-item').classList.add('picked'); tagsArray.push(tag); } }; const initTags = () => { var items = document.getElementsByClassName('tag-item'); tagsArray = []; }; function checkIfTagsMatch(arr1, arr2) { return arr1.every(item => arr2.includes(item)) ; } var sjs = new SimpleJekyllSearch({ searchInput: searchInput, resultsContainer: document.getElementById('search-results'), json: '/assets/search.json', searchResultTemplate: '<li class="result"><a href="{url}">{title}</a></li>', limit: 50, tagsArray: tagsArray, noResultsText: 'brak wyników', fuzzy: false }); initTags(); </script>
    </main>





        