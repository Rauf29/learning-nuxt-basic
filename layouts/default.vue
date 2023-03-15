<template>
  <title>Learning Nuxt</title>
    <div>
      <div>
        <ul>
        <li><NuxtLink to="/">Home</NuxtLink> </li>
        <li><NuxtLink to="/about">About</NuxtLink> </li>
        <li><NuxtLink to="/contact">Contact</NuxtLink> </li>
        <li><NuxtLink to="/post">All Post</NuxtLink> </li>
        <li><NuxtLink to="/contents">Content</NuxtLink> </li>
        
      </ul>
      </div>
      <slot />
      <div>
        Footer goes here
      </div>
    </div>
  </template>