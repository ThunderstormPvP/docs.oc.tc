---
layout: page

category: "Examples"
category_lead:  "XML File Examples"
title:  "Viridun Blitz"

---

[<i class="fa fa-share right-ref-link"></i>](/modules/main)
Specify the XML file version and then open the main map module and specify the maps name, version and objective.

    <?xml version="1.0"?>
    <map proto="{{site.current_proto}}">
    <name>Viridun Blitz</name>
    <version>1.4.4</version>
    <objective>Eliminate the other team before 10 minutes is up</objective>

<br/>
Specify the maps authors and contributors. Each author and contributors `contribution=""` attribute is set to their specific contribution to the map.

    <authors>
        <author uuid="27cf0cdd-c294-4163-a536-18e11360cc7b" contribution="Map design and layout"/> <!-- OurLoneHero -->
    </authors>
    <contributors>
        <contributor uuid="82c796a5-c033-43be-af30-fa06496995f9" contribution="Map design, aesthetic changes, and XML"/> <!-- IM_A_H0B0 -->
        <contributor uuid="97abb45c-e545-473d-9b93-e1b9b94a43ee" contribution="Design concepts and map design"/> <!-- ander301 -->
    </contributors>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/teams)
Define two teams, their [colors](/reference/formatting#chatColors) and names.

    <teams>
        <team id="blue-team" color="blue" max="50">Blue Team</team>
        <team id="red-team" color="dark red" max="50">Red Team</team>
    </teams>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/filters)
Define a fancy redstone filter. Prevents pistons from pushing anything other than fence blocks.

    <filters>
        <all id="allow-redstone">
            <any>
                <material>PISTON_BASE</material>
                <material>PISTON_EXTENSION</material>
                <material>PISTON_MOVING_PIECE</material>
                <material>PISTON_STICKY_BASE</material>
            </any>
            <any>
                <material>AIR</material><!-- Allow the piston to extend -->
                <material>FENCE</material><!-- Block being modified is a fence -->
            </any>
        </all>
    </filters>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/regions)
Define a `playable` region and apply the maps custom `allow-redstone` filter to it.

    <regions>
        <rectangle id="playable" min="-oo,-oo" max="oo,oo"/>
        <apply block="allow-redstone" region="playable"/>
    </regions>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/kits)
Each team kit has leather armor colored in their team color and they inherit the main spawn kit.

    <kits>
        <kit id="spawn">
            <item slot="0" material="stone sword"/>
            <item slot="1" enchantment="arrow infinite:1" material="bow"/>
            <item slot="28" amount="1" material="arrow"/>
            <item slot="2" amount="16" material="cooked chicken"/>
            <item slot="3" damage="8229" material="potion"/> <!-- potion of instant health 2 -->
            <potion duration="10" amplifier="1">heal</potion>
            <potion duration="20">damage resistance</potion>
        </kit>
        <kit id="red" parents="spawn">
            <helmet color="cd0000" material="leather helmet"/>
            <chestplate color="cd0000" material="leather chestplate"/>
            <leggings color="cd0000" material="leather leggings"/>
            <boots color="cd0000" enchantment="protection fall:2" material="leather boots"/>
        </kit>
        <kit id="blue" parents="spawn">
            <helmet color="0066cc" material="leather helmet"/>
            <chestplate color="0066cc" material="leather chestplate"/>
            <leggings color="0066cc" material="leather leggings"/>
            <boots color="0066cc" enchantment="protection fall:2" material="leather boots"/>
        </kit>
    </kits>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/spawns)
Define where the player spawns. Because the bases are complex multiple regions are defined for each team spawn. Each spawn also specifies the direction the player should face when spawning.

    <spawns>
        <spawns kit="blue">
            <spawn team="blue-team" yaw="0">
                <cuboid min="23,33,-60" max="29,33,-55"/>
                <cuboid min="24,33,-41" max="29,33,-46"/>
                <cuboid min="-32,33,-3" max="-28,33,2"/>
                <cuboid min="-23,79,-4" max="-18,79,2"/>
                <cuboid min="-18,87,-5" max="-12,87,-3"/>
            </spawn>
            <spawn team="blue-team" yaw="90">
                <cuboid min="40,37,-55" max="45,37,-58"/>
                <cuboid min="41,64,-71" max="35,64,-77"/>
                <cuboid min="47,72,-39" max="42,72,-44"/>
                <cuboid min="40,52,-15" max="32,52,-27"/>
                <cuboid min="13,60.5,13" max="14,60.5,16"/>
                <cuboid min="-17,33,13" max="-13,33,15"/>
            </spawn>
            <spawn team="blue-team" yaw="180">
                <cuboid min="-20,62,-6" max="-10,62,-2"/>
                <cuboid min="-1,33,-4" max="3,33,3"/>
                <cuboid min="-1,71,6" max="2,71,9"/>
                <cuboid min="-17,87,2" max="-12,87,4"/>
            </spawn>
        </spawns>
        <spawns kit="red">
            <!-- red spawns -->
            <spawn team="red-team" yaw="0">
                <cuboid min="-107,90,-21" max="-110,90,-25"/>
                <cylinder base="-99,63,-73" radius="3" height="0"/>
                <cuboid min="-92,37,25" max="-88,37,30"/>
            </spawn>
            <spawn team="red-team" yaw="90">
                <cylinder base="-91,76,-72,5" radius="1" height="0"/>
                <cuboid min="-72,65,-27" max="-72,65,-23"/>
            </spawn>
            <spawn team="red-team" yaw="180">
                <cylinder base="-98.5,84,-72.5" radius="2" height="0"/>
                <cuboid min="-109,79,-15" max="-102,79,-29"/>
                <cuboid min="-86,80,-11" max="-91,80,-18"/>
                <cuboid min="-97,76,-61" max="-101,76,-48"/>
                <cuboid min="-88,37,48" max="-84,37,52"/>
            </spawn>
            <spawn team="red-team" yaw="270">
                <cuboid min="-142,83,-39" max="-121,83,-35"/>
                <cuboid min="-110,65,-15" max="-103,65,-29"/>
                <cuboid min="-98,65,-43" max="-114,65,-36"/>
            </spawn>
        </spawns>
        <default yaw="90"><cylinder base="51,27,-7.5" radius="10" height="0"/></default>
    </spawns>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/gamemode_blitz)
Set the game type to blitz and specify a max run time of 10 minutes.

    <time>10m</time>
    <blitz>
        <lives>1</lives>
    </blitz>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/repair_remove_keep)
Specify that stone swords and bows get repaired when dropped or when the player picks one up.

    <toolrepair>
        <tool>stone sword</tool>
        <tool>bow</tool>
    </toolrepair>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/repair_remove_keep)
Remove specific items such as armor when they get dropped to prevent the map from getting cluttered.

    <itemremove>
        <item>leather helmet</item>
        <item>leather chestplate</item>
        <item>leather leggings</item>
        <item>leather boots</item>
        <item>arrow</item>
        <item>ladder</item>
        <item>cooked chicken</item>
        <item>glass bottle</item>
        <item>potion:0</item><!-- Remove water bottles -->
    </itemremove>

<br/>
[<i class="fa fa-share right-ref-link"></i>](/modules/gamemode_blitz)
Include the global blitz XML.

    <include src="blitz-global.xml"/>

<br/>
Close the main `<map>` module.

    </map>
