# QPS

QRE1113 Position Sensor (QPS).

This is an alternative sensorboard which differ from the original HPS in the following ways

* It uses the QRE1113 sensors. These sensors are smaller and allow for an easier-to-assemble and more accurate mechanical setup
* There are multiple sensors per board. This simplifies the mechanics
* It includes sensor protectors. These improve the mechanics of the board for the hammer impact, and act as blinders for the sensors,
reducing both the amount of IR light sent on nearby hammers, as well as keep the field of view of the phototransistor narrower,
improving directionality and reducing crosstalk
* It does not include neither current-limiter resistors for the LED, nor bias-resistors for the phototransistor, as such it allows for
more flexible powering schemes.

I have an untested design with 2 sensors per board, however I am not putting it here because I have not tested it. I have not tested
it because I have found that the version with 4x can be simply used for all hammers and keys: just leave some sensors unused (and not
connected). That is more cost effective than having versions with different number of sensors per board, at the expense of minimal
assembly complication.

## Flexibility in power supply -- BE CAREFUL!

The lack of current-limiter resistors means that you cannot power this board directly from a typical (i.e. constant-voltage) power supply,
or you will *immediately* burn all the LEDs in the board. You will have either use a current-limiter resistor which you will have to
add to the power line (good for a quick test) or
use a constant-current power supply, for example by putting several boards in series (connecting the + terminal of one board to the -
terminal of its neighbor and then connecting the first and last +/- terminals to the power supply). The advantage of the constant-current
power supply is two-fold:

* Reduces power consumption and hence produced heat by both the power supply and the sensorboards
* Eliminates the sensor-to-sensor variabilities, since each LED has a different forward-voltage -> when driven in current, all LED will
have the same intensity

## Read out

Also in this case you can add a resistor, in this case for biasing the phototransitor. In such a case you will have to add one on each
sensor. Alternatively, you can use a transimpedance amplifier, which has some advantages. See
[here](https://github.com/jkominek/piano-conversion/wiki/Analog-Stage-Theory-of-Operation) for details.


## Labeling

* + and - are the LED powering connections
* E and C are the Emitter and Collector of the phototransistor respectively


