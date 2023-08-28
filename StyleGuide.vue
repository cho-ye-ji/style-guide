<template>
  <div class="guide-wrap">
    <header class="guide-header">Emax Mobile Common Style<span> (Version. 1.0)</span></header>

    <div class="guide-lnb">
      <div class="guide-lnb-inner">
        <ul>
          <li v-for="(item, index) in menuItems" :key="index" :class="{ 'on': selectedItem === item }">
            <a :href="`#${index + 1}`" @click.prevent="selectMenuItem(item, index)">{{ item }}</a>
          </li>
        </ul>
      </div>
    </div>

    <main class="guide-content">
      <!-- Button -->
      <h2 id="1" class="guide-title gap-sm">Button</h2>
      <div class="guide-inner-wrap">
        <div class="view">
					<h3 class="sub-title">basic type</h3>
					<p class="desc">description descriptiondescriptiondescriptiondescriptiondescriptiondescriptiondescriptiondescriptiondescription</p>
					<div class="flex">
						<q-btn color="blue" label="default" />
						<q-btn outline label="outline" />
					</div>
					<h3 class="sub-title">full type</h3>
					<q-btn class="full-width" color="blue" label="full width" />
        </div>
        <div class="code">
          <pre>
            <code class="language-markup">
	// basic type
	&lt;q-btn color="blue" label="default" />

	&lt;q-btn outline label="outline" />


	// full type
	&lt;q-btn class="full-width" color="blue" label="full width" />
            </code>
          </pre>
        </div>                   
      </div>

      <!-- Typograpgy -->
      <h2 id="2" class="guide-title">Typograpgy</h2>
      <div class="guide-inner-wrap">
        
      </div>

      <!-- Menu -->
      <h2 id="3" class="guide-title">Typograpgy</h2>
      <div class="guide-inner-wrap">
        
      </div>

      <!-- Menu -->
      <h2 id="4" class="guide-title">Typograpgy</h2>
      <div class="guide-inner-wrap">
        
      </div>

      <!-- Menu -->
      <h2 id="5" class="guide-title">Typograpgy</h2>
      <div class="guide-inner-wrap">
        
      </div>
    </main>
  </div>
</template>
<script setup>
import { ref } from 'vue';
import 'prismjs/themes/prism.css'; // Prism.js 테마 스타일 import
import Prism from 'prismjs'; // Prism.js import
import 'prismjs/components/prism-javascript';
import 'prismjs/components/prism-css';
import 'prismjs/components/prism-markup';

const menuItems = [
  'Button',
  'Typograpgy',
  'Menu',
  'Pagination Menu',
  'Icon',
  'Badge&Label',
  'Checkbox',
  'Radio',
  'Selectbox',
  'Input',
  'Tab',
  'Table',
  'List',
  'Design Module',
  'Popup',
  'Steps',
  'Etc',
  'Faq'
];

const selectedItem = ref(menuItems[0]);

const selectMenuItem = (item, index) => {
  selectedItem.value = item;
  scrollToElement(index + 1);
};

const scrollToElement = (id) => {
  const element = document.getElementById(id);
  if (element) {
    const offsetTop = element.offsetTop - 90;
    window.scrollTo({
      top: offsetTop,
      behavior: 'smooth',
    });
  }
};

</script>
<style scoped>
@import 'prismjs/themes/prism.css';
.gap-sm {
  margin-top: 10px;
}
.guide-wrap {
	width: 100%;
}
.guide-header {
	position: fixed;
	width: 100%;
	height: 65px;
	font-size: 18px;
	font-weight: bold;
	color: #222;
	z-index: 100;
	background-color: #fff;
	box-shadow: 0 3px 4px rgba(0, 0, 0, 0.05);
	padding: 24px 0 24px 40px;
	letter-spacing: -0.5px;
}
.guide-header span {
	font-size: 14px;
}
.guide-lnb {
	position: fixed;
	width: 250px;
	height: 100%;
	background-color: #fff;
	border-right: 1px solid #e8e8e8;
	padding: 100px 0 0 0px;
	z-index: 1;
	overflow-x: hidden;
}
.guide-lnb-inner {
	position: relative;
	overflow: hidden;
	width: 100%;
	height: 100%;
}
.guide-lnb-inner ul a {
	display: block;
  color: #222;
}
.guide-lnb ul {
	width: 100%;
	position: absolute;
	inset: 0px;
	overflow: scroll;
	margin-right: -17px;
	margin-bottom: -17px;
}
.guide-lnb ul li {
	width: 100%;
	height: 50px;
	line-height: 50px;
	font-size: 16px;
	color: #222;
	padding-left: 40px;
	cursor: pointer;
}
.guide-lnb ul li:hover {
	color: #338DBF;
}
.guide-lnb ul li.on {
	background: #f0f4ff;
	color: #338DBF;
	transition: 0.2s;
}
.guide-lnb ul li.on a {
  font-weight: 800;
  color: #338DBF;
}
.guide-content {
	padding: 80px 30px 80px 280px;
}
.guide-title {
	position: relative;
	padding: 35px 0 15px 0;
	font-size: 30px;
	font-weight: 500;
	color: #222;
	margin-bottom: 20px;
}
::-webkit-scrollbar {
	width: 4px;
}
::-webkit-scrollbar-thumb:vertical {
	background-color: #338DBF;
  border-radius: 5px;
}
::-webkit-scrollbar-thumb:horizontal {
	background-color: #ededed;
}
/*.guide-inner*/
.guide-title {
	position: relative;
	padding: 0 0 15px 0;
	font-size: 30px;
	font-weight: 500;
	color: #222;
	margin-bottom: 20px;
}
.guide-inner-wrap {
	display: flex;
	gap: 10px;
	width: 100%;
  min-height: 700px;
}
.guide-inner-wrap > div {
	overflow-x: auto;
	flex: 0 0 calc(50% - 5px);
	border: 1px solid #ddd;
}
.guide-inner-wrap + .guide-title {
	margin-top: 50px;
}
.guide-inner-wrap .sub-title {
	font-size: 16px;
	margin-top: 20px;
	margin-bottom: 5px;
	font-weight: 800;
}
.guide-inner-wrap .view {
	padding: 10px;
	display: flex;
	gap: 10px;
	flex-flow: column;
}
.guide-inner-wrap .view .flex {
	display: inline-flex;
	flex-flow: row;
	gap: 10px;
}
.guide-inner-wrap .view .desc {
	word-break: break-all;
}
.guide-inner-wrap .code {
	border: none;
}
.code-box {
	clear: both;
	border: 1px solid #ddd;
	padding: 1.25em;
	margin-bottom: 10px;
}
.code-box > h3:first-child {
	margin-bottom: 30px;
	font-size: 20px;
	line-height: 20px;
}
.code-box:after {
	content: '';
	display: block;
	clear: both;
}
.code-box > * {
	margin: 5px 0 5px 0;
}
.code-box#tree-menu-demo > * {
	margin: 0;
}
.code-box .content-exp {
	font-size: 14px;
	color: #888;
	margin-left: 10px;
}
pre[class*="language-"] {
	height: 100%;
	margin: 0;
}
</style>
