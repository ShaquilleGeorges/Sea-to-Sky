# Sea-to-Sky

This is the code I used to have the enemy AI partol around an area.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class EnemyAI : MonoBehaviour
{

    GameObject player;
    UnityEngine.AI.NavMeshAgent enemy;

    // Start is called before the first frame update
    void Start()
    {
        player = GameObject.FindGameObjectWithTag("Player");

        if (player == null)
        {
            Debug.Log("Did you tag your Player or FPS Controller?");
        }

        enemy = GetComponent<UnityEngine.AI.NavMeshAgent>();


    }

    // Update is called once per frame
    void Update()
    {
        if (player != null)
        {
            enemy.destination = player.transform.position;
        }
            
    }
}
