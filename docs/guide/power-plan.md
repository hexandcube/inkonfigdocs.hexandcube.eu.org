# Power Plan

### Select Power Plan

Let's you change the Power Plan to one of the 3 deafult plans: Balanced, High Performance, or Power Saver.

System Default: `Balanced`

=== "Balanced"

    ```batch
    powercfg -setactive 381b4222-f694-41f0-9685-ff5bb260df2e
    ```
=== "High Performance"

    ```batch
    powercfg -setactive 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c
    ```

=== "Power Saver"

    ```batch
    powercfg -setactive a1841308-3541-4fab-bc81-f71556f20b4a
    ```

### Hibernation

Toggles the Hibernation feature.

System default: `Disabled`

=== "Enabled"

    ```batch
    powercfg -H ON
    ```
=== "Disabled"

    ```batch
    powercfg -H OFF
    ```

## On AC Power

### Lid Close Action

Changes the action that is performed when closing the lid of the laptop while on AC power.
This option doesn't affect desktop computers.

System default: `Sleep`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 5ca83367-6e45-459f-a27b-476b1d01c936 ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |


### Power Button Action

Changes the action that is performed when pressing the power button while on AC power.

System default: `Shut Down`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 7648efa3-dd9c-4e3e-b566-50f929386280 ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |
| `4`         | Turn off the display                 |


### Sleep Button Action

Changes the action that is performed when pressing the sleep button while on AC power.

System default: `Sleep`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 96996bc0-ad50-47ec-923b-6f41874dd9eb ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |
| `4`         | Turn off the display                 |


## On Battery Power

### Lid Close Action

Changes the action that is performed when closing the lid of the laptop while on battery (DC) power.
This option doesn't affect desktop computers.

System default: `Sleep`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 5ca83367-6e45-459f-a27b-476b1d01c936 ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |


### Power Button Action

Changes the action that is performed when pressing the power button while on battery (DC) power.

System default: `Shut Down`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 7648efa3-dd9c-4e3e-b566-50f929386280 ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |
| `4`         | Turn off the display                 |


### Sleep Button Action

Changes the action that is performed when pressing the sleep button while on battery (DC) power.

System default: `Sleep`

```batch
powercfg -setacvalueindex SCHEME_CURRENT 4f971e89-eebd-4455-a8de-9e59040e7347 96996bc0-ad50-47ec-923b-6f41874dd9eb ${VALUE}
```

#### Possible values

| Value       | Option                               |
| ----------- | ------------------------------------ |
| `0`         | Do nothing                           |
| `1`         | Sleep                                |
| `2`         | Hibernate                            |
| `3`         | Shut down                            |
| `4`         | Turn off the display                 |