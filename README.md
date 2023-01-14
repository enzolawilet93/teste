using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float moveSpeed = 5f;

    private Rigidbody2D rb;
    private Vector2 moveAmount;

    private void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    private void Update()
    {
        float moveX = Input.GetAxis("Horizontal");
        float moveY = Input.GetAxis("Vertical");

        moveAmount = new Vector2(moveX, moveY);

        if (moveAmount != Vector2.zero)
        {
            rb.MovePosition(rb.position + moveAmount * moveSpeed * Time.deltaTime);
        }
    }
}


