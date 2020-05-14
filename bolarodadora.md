using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class BallControl : MonoBehaviour
{
    //Variables publicas
	public float ballForce = 1.0f;

	//Variables privadas
	private Vector3 horizontalInput, verticalInput;

	// Use this for initialization
	void Start () {
		
	}
	
	// Update is called once per frame
	void Update ()
    {

		//Vamos a empujar la bola en la direccion que pulse el usuario


		//Primero calculamos el input horizontal y vertical
		horizontalInput = transform.right * Input.GetAxis("Horizontal");
		verticalInput = transform.forward * Input.GetAxis("Vertical");

        //Segundo empujamos la bola con la fuerza ballforce
		GetComponent<Rigidbody>().AddForce( (horizontalInput + verticalInput) * ballForce);
    
	}
} 
