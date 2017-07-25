---
layout: default
---

<div class="container">
<div class="jumbotron">
<h1>XML Documentation</h1>
<p class="lead">Documentation on XML files that are required for each map added to the servers</p>
</div>
<section>
<div class="page-header">
<h1>Welcome</h1>
</div>
<div class="row">
<div class="col-sm-6" markdown="1">

### Thunderstorm PvP
This site currently documents a special fork of PGM which is running on Thunderstorm PvP. All maps being submitted to our servers will be required to adhere to the XML format defined on this site.

### What Do XML Files Do?
XML files configure how the PGM plug-in manages the map during game-play. Any map released on the Thunderstorm PvP requires a XML file to function properly. The XML defines aspects of the game such as spawn points, teams, kits and more. Each file is unique to its map, however the individual components are generic and are used on many different maps.


### Writing XML Files
Almost every generic text editor can create and edit XML files, however editors designed for XML can automatically indent and syntax hi-light your code to help spot mistakes.

We recommend that you use [Sublime Text](http://www.sublimetext.com) to create and edit XML files.

To keep your XML file clean & readable you should properly indent them using 4 spaces and only specify elements or attributes you intend to use.

### Releasing Your Map
Before releasing your map for the map developers to test, we strongly recommend you package your map following [these guidelines](/guides/packaging/cleaning_files).
This will speed up the time it takes to get your map ready for testing.

</div>
<div class="col-sm-6" markdown="1">
### Using These Docs
This documentation is intended to list all currently available XML modules, their attributes & sub-elements; and describe how the modules work and interact with the player. It is intended to be used as a reference when coding the XML files accompanying a map to ensure that the XML is valid and works like it is supposed to.

All attributes or sub-elements for a element or module are listed in a table and required attributes or sub-elements are marked in red. In the following example the `color` attribute is required but `id` is not. The attribute or elements default value is also listed if there is one.

##### Table Example
<div class="table-responsive">
  <table class="table table-striped table-condensed">
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>Unique identifier used to reference this element.</td>
        <td>
          <span class="label label-primary">String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>color</code>
        </td>
        <td>
          <span class="label label-danger">Required</span>
          This examples color.
        </td>
        <td>
          <a href="/reference/colors"> Dye Color Name</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>cow</code>
        </td>
        <td>This example has a pet cow.</td>
        <td>
          <span class="label label-primary">true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
</div>
</div>
</section>
</div>
