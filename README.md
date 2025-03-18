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
The black cube represents the collision point.

