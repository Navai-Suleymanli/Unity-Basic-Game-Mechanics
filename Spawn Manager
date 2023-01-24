using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpawnManager : MonoBehaviour
{
    public GameObject enemyPrefab;
    public GameObject powerupPrefab;
    private float spawnRange = 9.0f;
    public int enemyCount;
    private int waveCount = 1;

    // Start is called before the first frame update
    void Start()
    {
        SpawnEnemyWave(waveCount);
        Instantiate(powerupPrefab, GenerateSpawnPos(), powerupPrefab.transform.rotation);

    }

    void SpawnEnemyWave(int enemiesToSpawn)
    {
        for (int i = 0; i < enemiesToSpawn; i++)
        {
            Instantiate(enemyPrefab, GenerateSpawnPos(), enemyPrefab.transform.rotation);
        }
    }

    // Update is called once per frame
    void Update()
    {
        enemyCount = FindObjectsOfType<Enemy>().Length;
        if(enemyCount == 0)
        {
            waveCount++;
            SpawnEnemyWave(waveCount);
            Instantiate(powerupPrefab, GenerateSpawnPos(), powerupPrefab.transform.rotation);
        }
    }

    private Vector3 GenerateSpawnPos()
    {
        float spwanPosX = Random.Range(-spawnRange, spawnRange);
        float spwanPosZ = Random.Range(-spawnRange, spawnRange);

        Vector3 randomPos = new Vector3(spwanPosX, 0.13f, spwanPosZ);

        return randomPos;
    }
}
