# Unity FSM (Finite State Machine) Pattern

## Example

```csharp
using System;
using UnityEngine;

public class SampleController : MonoBehaviour
{

    public enum State
    {

        Playing,

        Paused

    }

    [SerializeField]
    private State _state = State.Playing;

    public State state
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
        if (state.Equals(State.Playing))
        {
            StatePlayingSwitch();
        }
        else if (state.Equals(State.Paused))
        {
            StatePausedSwitch();
        }
    }

    private void RunStateLoop()
    {

        if (state.Equals(State.Playing))
        {
            StatePlayingLoop();
        }
        else if (state.Equals(State.Paused))
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
