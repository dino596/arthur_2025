---
layout: base
title: Title Page
description: Introduction to my blog
author: Arthur Liu
hide: true
---

Welcome to Arthur Liu's CSA blog.

[![image.png](https://i.postimg.cc/90K7ymVs/image.png)](https://postimg.cc/zHwvr1yk)

### Schedule

<table id="schedule">
  <thead>
    <tr>
      <th>Classes</th>
      <th>Assignments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>CompSci A</td>
      <td>
        <ul id="csa-assignments"></ul>
        <input type="text" id="csa-assignment" placeholder="add assignment">
        <button onclick="add('csa')">Add Assignment</button>
      </td>
    </tr>
    <tr>
      <td>World Lit</td>
      <td>
        <ul id="lit-assignments"></ul>
        <input type="text" id="lit-assignment" placeholder="add assignment">
        <button onclick="add('lit')">Add Assignment</button>
      </td>
    </tr>
    <tr>
      <td>Physics E&M</td>
      <td>
        <ul id="enm-assignments"></ul>
        <input type="text" id="enm-assignment" placeholder="add assignment">
        <button onclick="add('enm')">Add Assignment</button>
      </td>
    </tr>
    <tr>
      <td>Statistics</td>
      <td>
        <ul id="stats-assignments"></ul>
        <input type="text" id="stats-assignment" placeholder="add assignment">
        <button onclick="add('stats')">Add Assignment</button>
      </td>
    </tr>
    <tr>
      <td>Civics</td>
      <td>
        <ul id="civics-assignments"></ul>
        <input type="text" id="civics-assignment" placeholder="add assignment">
        <button onclick="add('civics')">Add Assignment</button>
      </td>
    </tr>
  </tbody>
</table>

<script>
  // classes
  const CLASSES = ['csa', 'lit', 'enm', 'stats', 'civics'];

  // load assignments from local storage
  document.addEventListener('DOMContentLoaded', function() {
    CLASSES.forEach(cls => {
      const assignments = JSON.parse(localStorage.getItem(cls + '-assignments')) || [];
      assignments.forEach(assignment => list(cls, assignment));
    });
  });

  // add assignments
  function add(classId) {
    const input = document.getElementById(classId + '-assignment');
    const value = input.value.trim();
    if (value) {
      list(classId, value);
      save(classId, value);
      input.value = '';
    }
  }

  // add the assignment to the list
  function list(classId, value) {
    const ul = document.getElementById(classId + '-assignments');
    const li = document.createElement('li');
    li.textContent = value;
    li.onclick = function() {
      ul.removeChild(li);
      remove(classId, value);
    };
    ul.appendChild(li);
  }

  // save the assignment to local storage
  function save(classId, value) {
    const assignments = JSON.parse(localStorage.getItem(classId + '-assignments')) || [];
    assignments.push(value);
    localStorage.setItem(classId + '-assignments', JSON.stringify(assignments));
  }

  // remove on click
  function remove(classId, value) {
    assignments = JSON.parse(localStorage.getItem(classId + '-assignments')) || [];
    localStorage.setItem(classId + '-assignments', JSON.stringify(assignments.filter(assignment => assignment !== value)));
  }
</script>
