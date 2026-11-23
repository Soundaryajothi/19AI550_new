# Experiment 6: Implementing Jumping Behavior in Unity 
### REGISTER NUMBER : 212223220108
### NAME: SOUNDARYA J
### AIM: 
To implement a jumping behavior for a player-controlled character in Unity using Rigidbody physics and user input, where pressing the spacebar while in the air causes the player to move down. 
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```

### Program:
```
using UnityEngine;

   public class Jump : MonoBehaviour
   {
       public float jumpForce = 5f;
       private bool isGrounded;
       private Rigidbody rb;

       void Start()
       {
           rb = GetComponent<Rigidbody>();
       }

       void Update()
       {
           if (isGrounded && Input.GetKeyDown(KeyCode.Space))
           {
               rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
               isGrounded = false;
           }
       }

       private void OnCollisionEnter(Collision collision)
       {
           if (collision.gameObject.CompareTag("Ground"))
           {
               isGrounded = true;
           }
       }
   }
```

### Output:

## Initially player in air:
<img width="850" alt="image" src="https://github.com/user-attachments/assets/7a669489-0f94-4e03-a42c-16db1298e719" />

## After player jumped:
<img width="850" alt="image" src="https://github.com/user-attachments/assets/3c43b7e2-e1c4-4e34-822c-ad2aff291b84" />







### Result:
Thus the simple seek behavior was implemented successfully.
.
