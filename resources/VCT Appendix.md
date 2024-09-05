# Appendix

### Game data

<table>
  <tr>
    <td> Event Type </td>
    <td> Example </td>
  </tr>
  <tr>
    <td> player_died </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "playerDied": {
      "deceasedId": {
        "value": 2
      },
      "weapon": {
        "fallback": {
          "displayName": "",
          "inventorySlot": {
            "slot": "PRIMARY"
          },
          "guid": "EE8E8D15-496B-07AC-E5F6-8FAE5D4C7B1A"
        },
        "type": "UNKNOWN"
      },
      "assistants": [
        {
          "assistantId": {
            "value": 7
          }
        }
      ],
      "killerId": {
        "value": 6
      }
    }
  }

```
</td>
  </tr>
    <tr>
    <td> round_decided </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "roundDecided": {
      "result": {
        "roundNumber": 14,
        "spikeModeResult": {
          "attackingTeam": {
            "value": 21
          },
          "cause": "ELIMINATION",
          "defendingTeam": {
            "value": 20
          }
        },
        "winningTeam": {
          "value": 20
        }
      }
    }
  }
```
</td>
  </tr>

<tr>
    <td> round_started </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "roundStarted": {
      "roundNumber": 11,
      "spikeMode": {
        "currentRound": 11,
        "attackingTeam": {
          "value": 20
        },
        "completedRounds": [
          {
            "roundNumber": 1,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 2,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 3,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "DETONATE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 4,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 5,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 6,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 7,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 8,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 9,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 10,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          }
        ],
        "roundsToWin": 13,
        "defendingTeam": {
          "value": 21
        }
      }
    }
  }
```
</td>
  </tr>

 <tr>
    <td> round_ended </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "roundEnded": {
      "roundNumber": 8
    }
  }
```
</td>
  </tr>

 <tr>
    <td> player_spawn </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "playerSpawn": {
      "player": {
        "value": 2
      }
    }
  }
```
</td>
  </tr>

 <tr>
    <td> spike_status </td>
    <td>
      
``` JavaScript
{
  "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
  "spikeStatus": { "carrier": { "value": 4 }, "status": "IN_HANDS" }
}
```
</td>
  </tr>

 <tr>
    <td> inventory_transaction </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "inventoryTransaction": {
      "player": {
        "value": 4
      },
      "weapon": {
        "fallback": {
          "displayName": "",
          "inventorySlot": {
            "slot": "PRIMARY"
          },
          "guid": "9C82E19D-4575-0200-1A81-3EACF00CF872"
        },
        "type": "UNKNOWN"
      },
      "transactionType": "PURCHASE"
    }
  }
```
</td>
  </tr>

 <tr>
    <td> game_decided </td>
    <td>
      
``` JavaScript
{
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "gameDecided": {
      "state": "WINNER_DECIDED",
      "winningTeam": {
        "value": 20
      },
      "spikeMode": {
        "currentRound": 23,
        "attackingTeam": {
          "value": 21
        },
        "completedRounds": [
          {
            "roundNumber": 1,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 2,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 3,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "DETONATE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 4,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 5,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 6,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 7,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 8,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 9,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 10,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 11,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "TIME_EXPIRED",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 12,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 20
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 21
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 13,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 14,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 15,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 16,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "DETONATE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 17,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 21
            }
          },
          {
            "roundNumber": 18,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 19,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 20,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 21,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 22,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "SPIKE_DEFUSE",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          },
          {
            "roundNumber": 23,
            "spikeModeResult": {
              "attackingTeam": {
                "value": 21
              },
              "cause": "ELIMINATION",
              "defendingTeam": {
                "value": 20
              }
            },
            "winningTeam": {
              "value": 20
            }
          }
        ],
        "roundsToWin": 13,
        "defendingTeam": {
          "value": 20
        }
      }
    }
  }
```
</td>
  </tr>

 <tr>
    <td> round_ceremony </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "roundCeremony": {
      "fallback": {
        "guid": "00000000000000000000000000000000",
        "displayName": "AceCeremony_C"
      },
      "type": "ACE"
    }
  }
```
</td>
  </tr>

 <tr>
    <td> damage_event </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "damageEvent": {
      "location": "HEAD",
      "causerId": {
        "value": 2
      },
      "victimId": {
        "value": 6
      },
      "killEvent": true,
      "damageAmount": 113.998192
    }
  }
```
</td>
  </tr>

 <tr>
    <td> player_downed </td>
    <td>
      
``` JavaScript
{
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "playerDowned": {
      "downedId": {
        "value": 3
      },
      "weapon": {
        "fallback": {
          "displayName": "",
          "guid": "EE8E8D15-496B-07AC-E5F6-8FAE5D4C7B1A",
          "inventorySlot": {
            "slot": "PRIMARY"
          }
        },
        "type": "UNKNOWN"
      },
      "downedById": {
        "value": 6
      }
    }
  }
```
</td>
 </tr>

 <tr>
    <td> player_revived </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "playerRevived": {
      "revivedById": {
        "value": 6
      },
      "revivedId": {
        "value": 9
      }
    }
  }
```
</td>
  </tr>

 <tr>
    <td> round_rollback </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "roundRollback": {
      "rolledBackToRound": 0
    }
  }
```
</td>
  </tr>

 <tr>
    <td> observer_target </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:004b09b1-4dc9-4185-baff-9b1c66b3ef99",
    "observerTarget": {
      "targetId": {
        "value": 10
      },
      "observerId": {
        "value": 16
      }
    }
  }
```
</td>
  </tr>

 <tr>
    <td> game_ended </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:007fa549-3b41-428f-bf99-c99cec7a8b1c",
    "gameEnded": {},
  }
```
</td>
  </tr>

 <tr>
    <td> ability_used </td>
    <td>
      
``` JavaScript
 {
    "platformGameId": "val:007fa549-3b41-428f-bf99-c99cec7a8b1c",
    "abilityUsed": {
      "chargesConsumed": 1,
      "ability": {
        "fallback": {
          "displayName": "",
          "inventorySlot": {
            "slot": "ABILITY_2"
          },
          "guid": "117ED9E3-49F3-6512-3CCF-0CADA7E3823B"
        },
        "type": "UNKNOWN"
      },
      "playerId": {
        "value": 8
      }
    }
  }
```
</td>
  </tr>
 
</table>
