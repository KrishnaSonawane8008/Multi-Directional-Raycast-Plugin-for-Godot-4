Using Godot v4.2.1 stable
<br>
<h1>How to Setup</h1>
Just ignore the blender files and add the Multi_RayCast folder to your addons folder, go to project settings in your Godot editor and enable the "Multijoint Raycast" plugin option. You will then be able to add a new node called "Spider Leg" to your project. Now you have the plugin, you now have access to the collision point, the id of the collider, a reference to the collider and the normal of the face with which the raycast is colliding. All this can be accessed via:
<li>Multi_Raycast.normal</li>
<li>Multi_Raycast.collider</li>
<li>Multi_Raycast.collider_id</li>
<li>Multi_Raycast.collision_point</li>
<br>
Where "Multi_Raycast" is the a reference to the "Spider Leg" Node.
<h3>Plugin UI</h3>
The right side panel containing node properties will contain a SpiderLeg dropdown, which when expanded will show two buttons, namely "add" and "remove". The node works with a hierarchy system with the root ray at the top and the remaining rays being below the ones before them, the "add" button adds a new ray at the bottom of the hierarchy and the "remove" button removes a ray from the bottom of the hierarchy . 
<br>
<br>
You can see how the UI works here:
<video src="https://github.com/user-attachments/assets/44221e2f-f2ae-4234-8984-056a6226fd67"></video>
This hierarchy is related to collision detection, that means collision is detected closer to the root, which means if there are two colliding bodies currently colliding with the ray_casts, then only the collision with the body, closer to the root in the hierarchy, will be detected and the other will be ignored. This behaviour can be see clearly below:
<br>
<br>
<video src="https://github.com/user-attachments/assets/7197525c-3053-471c-a36a-7d33d0d74ea1"></video>
<br>
The black cube represents the collision point.
<br>
<h1>How it works</h1>
The black cube is the colision point and each blue line between the red cubes represent a RayCast. A RayCast in Godot (and in any other game engine) is a ray used for collision detection. Any colliding object between a raycast is supposed to report its collision related info to the entity requesting it. My plugin is the same except it uses multiple RayCasts which can be arranged in any position you want(as shown in the UI video) and then the arrangement serves as a giant raycast which is bent in desired directions, bascially its a crooked racast which works as the original concept.
<br>
<br>
This is possible because of the Godot <a href="https://docs.godotengine.org/en/stable/classes/class_physicsrayqueryparameters3d.html">PhysicsRayQueryParameters3D class</a> which allows you to get the collision info between any two points in world space, what results is a raycast that can bend in multiple directions and detect collisions in multiple directions:
<br>
<video src="https://github.com/user-attachments/assets/03ee4670-ac27-4610-83ae-2ecdbc792458"></video>
<h1>Some Limitations in UI</h1>
Because i made this plugin in a rush, i wasn't able to implement some of the common features in the editor like the ability to duplicate a node, so if you try to duplicate a node, it will be glitched, so please don't try to do so, instead just make the required hierarchy again. Thank You.
<h1>Resources</h1>
Ray-casting :- https://docs.godotengine.org/en/stable/tutorials/physics/ray-casting.html
PhysicsRayQueryParameters3D :- https://docs.godotengine.org/en/stable/classes/class_physicsrayqueryparameters3d.html

