# THE-NOV-TO

The Diffuse function simulates the overall brightness changes of a surface under illumination. It obtains the surface normal direction N and the main light source direction L, then performs a dot product on N and L. If N faces the light source, the dot product is positive, indicating the surface is brighter. The dot product result is multiplied by the light source color, and then multiplied by the object's surface color. The Specular function simulates specular reflection. It obtains the light source direction L and the view direction V, calculates the specular direction based on L and V, and then performs a dot product with the normal direction N. The closer the specular direction is to the reflection direction, the brighter the specular reflection.

<img width="696" height="443" alt="image" src="https://github.com/user-attachments/assets/6d22b6da-69d6-4093-a833-e9c200649d5f" />

<img width="692" height="337" alt="image" src="https://github.com/user-attachments/assets/358383a2-e230-436e-b353-849624333761" />


First, the Time node provides a continuously increasing time value. By multiplying Time by a velocity parameter, a controllable offset is generated to drive the movement of the water ripples. Then, Multiply controls the speed of the ripple movement; a larger value results in faster flow. Next, it's input to the Offset port of the Tiling And Offset node to continuously change the UV coordinates of the sampled texture. Because the output UV of Tiling And Offset changes over time, it creates a continuous water flow effect. The dynamic UV is then input to the Sample Texture 2D (Normal Map) node. The Normal Map's color texture contains information about the subtle waves on the water surface. As the UV changes, the normal texture appears to flow, simulating the movement of water ripples. Therefore, Sample Texture 2D outputs a normal vector (RGB) for subsequent lighting calculations. Finally, to make the visual effect of the ripples controllable, the sampled normal undergoes a Multiply operation.

<img width="691" height="355" alt="image" src="https://github.com/user-attachments/assets/70d70375-d81e-40cb-a749-ec4870760416" />

<img width="811" height="387" alt="image" src="https://github.com/user-attachments/assets/cbeb1225-8b42-47ab-818e-07d120d23254" />
























