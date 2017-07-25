---
layout: page

category: "Modules"
title:  "Rush"

---

Rush is essentially a racing game mode. A map will define three main regions, a spawn point, start line, and finish line. When players spawn on the map, spectators originally spawn at the spawn-point. Players will then be picked by random one after another until everyone has had their turn. Scores are calculated by the amount of time it takes for a player to complete the course. If a player never passes the start line they will be given a score of 1. Player's who do not pass the finish line or die will get a number calculated from their last time. The player with the highest score (shortest time) will win the match.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Rush Element</th>
        <th>Description</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<rush> </rush>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>A node containing the rush gamemode settings and regions.</td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<time-limit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The default amount of time each player will have to complete the course
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<spawn-point>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The location where players spawn
        </td>
        <td>
          <a href='/modules/regions'>Bounded Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<start-line>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The region a player must enter to start their timer
        </td>
        <td>
          <a href='/modules/regions'>Bounded Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<finish-line>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The region a player must enter to end their turn
        </td>
        <td>
          <a href='/modules/regions'>Bounded Region</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Rush Attributes</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Type</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>regenerate</code>
        </td>
        <td>Reset the map to it's original state after each turn.</td>
        <td>
          <span class='label label-primary'>True/False</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>countdown</code>
        </td>
        <td>The number in seconds a player is given before their turn begins.</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>5</td>
      </tr>
    </tbody>
  </table>
</div>

Example:

    <!-- Regenerate the map and have a countdown of 3 seconds  -->
    <rush regenerate='true' countdown='3'>

     <!-- A time limit of 60 seconds -->
     <time-limit>60</time-limit>

     <!-- The spawn point for spectators -->
     <spawn-point yaw="180" pitch="0">
        <block>0.5,70,6.5</block>
     </spawn-point>

     <!-- The start line region -->
     <start-line>
        <rectangle min="-7,-5" max="7,-3" />
     </start-line>

     <!-- The finish line region -->
     <finish-line>
        <rectangle min="-7,-51" max="7,-49" />
     </finish-line>
     
    </rush>
