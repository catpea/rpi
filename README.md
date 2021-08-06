# rpi
Raspberry Pi Notes

## Bluetooth Audio

### Connect Bluetooth Headphones

use ```bluetoothctl``` to trust pair connect (use scan on/off to get the address)

### Use Bluetooth Device

edit/create ```/etc/asound.conf``` or ```~/.asoundrc```

```cson
pcm.!default {
  type plug
  slave {
      pcm {
          type bluealsa
          device ENTER_BLUETOOTH_DEVICE_ADDRESS_HERE
          profile "a2dp"
      }
  }
  hint {
      show on
      description "Marshall MID"
  }
}
```

### USB Audio

Use ```aplay -l``` to get card number, edit 

and edit /usr/share/alsa/alsa.conf changing ctl/pcm .card to 1

```ini
defaults.ctl.card 1
defaults.pcm.card 1
```
