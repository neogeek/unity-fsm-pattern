# Unity FSM (Finite State Machine) Pattern

## Example

```csharp
using System;
using UnityEngine;

public class SampleController : MonoBehaviour
{

    public enum STATE
    {

        Playing,

        Paused

    }

    [SerializeField]
    private STATE _state = STATE.Playing;

    public STATE state
    {
        get => _state;
        private set
        {
            if (_state.Equals(value))
            {
                return;
            }

            Debug.Log($"Switched from state {_state} to {value}.");

            _state = value;

            RunStateSwitch();
        }
    }

    private void RunStateSwitch()
    {
        if (state.Equals(STATE.Playing))
        {
            StatePlayingSwitch();
        }
        else if (state.Equals(STATE.Paused))
        {
            StatePausedSwitch();
        }
    }

    private void RunStateLoop()
    {

        if (state.Equals(STATE.Playing))
        {
            StatePlayingLoop();
        }
        else if (state.Equals(STATE.Paused))
        {
            StatePausedLoop();
        }

    }

    private void Update()
    {
        RunStateLoop();
    }

    private void StatePlayingSwitch()
    {
        throw new NotImplementedException();
    }

    private void StatePlayingLoop()
    {
        throw new NotImplementedException();
    }

    private void StatePausedSwitch()
    {
        throw new NotImplementedException();
    }

    private void StatePausedLoop()
    {
        throw new NotImplementedException();
    }

}
```
