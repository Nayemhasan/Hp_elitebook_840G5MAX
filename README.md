# Hp_elitebook_840G5MAX
Max fan speed with custom power plan to get max performance from HP ELITEBOOK 840 G5
## About the fan xml
- fan xml stripped form the latest bios
- adjusted Ec Poll Interval to 100ms to better cool off the cpu
- auto mode kicks in faster than stock to max speed
- idle to max temp range with mod 35°-70°C and all cores to 3.5 GHZs
## About the powerplan
- maxed out everything even on battery power mode too *enable dc turbo boost from bios
- process states maxed out to 100% for no reason*

## What's in the code?
`🍉Fan xml to the max`
```bash
<?xml version="1.0"?>
<FanControlConfigV2 xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <NotebookModel>HP EliteBook 840 G5</NotebookModel>
  <EcPollInterval>100</EcPollInterval>
  <ReadWriteWords>false</ReadWriteWords>
  <CriticalTemperature>60</CriticalTemperature>
  <Author>Watermelon🍉</Author>
  <FanConfigurations>
    <FanConfiguration>
      <ReadRegister>46</ReadRegister>
      <WriteRegister>47</WriteRegister>
      <MinSpeedValue>88</MinSpeedValue>
      <MaxSpeedValue>48</MaxSpeedValue>
      <ResetRequired>true</ResetRequired>
      <FanSpeedResetValue>255</FanSpeedResetValue>
      <FanDisplayName>CPU fan</FanDisplayName>
      <TemperatureThresholds></TemperatureThresholds>
      <FanSpeedPercentageOverrides>
      <FanSpeedPercentageOverride>
      <FanSpeedPercentage>0</FanSpeedPercentage>
      <FanSpeedValue>255</FanSpeedValue>
      </FanSpeedPercentageOverride>
      </FanSpeedPercentageOverrides>
      </FanConfiguration>
      </FanConfigurations>
      <RegisterWriteConfigurations>
      <RegisterWriteConfiguration>
      <WriteMode>Set</WriteMode>
      <WriteOccasion>OnInitialization</WriteOccasion>
      <Register>34</Register>
      <Value>1</Value>
      <ResetRequired>true</ResetRequired>
      <ResetValue>1</ResetValue>
      <Description>Select thermal zone</Description>
      </RegisterWriteConfiguration>
      <RegisterWriteConfiguration>
      <WriteMode>Set</WriteMode>
      <WriteOccasion>OnInitialization</WriteOccasion>
      <Register>38</Register>
      <Value>28</Value>
      <ResetRequired>true</ResetRequired>
      <ResetValue>0</ResetValue>
      <Description>Fake thermal zone temperature</Description>
    </RegisterWriteConfiguration>
  </RegisterWriteConfigurations>
</FanControlConfigV2>
```
`🍉Powerplan`
```bash
$laptopSettingsCommands = @(
    "powercfg -setacvalueindex $guid SUB_VIDEO VIDEOIDLE 0",
    "powercfg -setacvalueindex $guid SUB_VIDEO BRIGHTNESS 100",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDCLOSEACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS POWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS SLEEPBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDOPENPOWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS POWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS SLEEPBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDOPENPOWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEMAX 100",
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEMIN 100",
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEPCT 100"
)

# Configure power plan settings for desktops
$desktopSettingsCommands = @(
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEMAX 100",
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEMIN 100",
    "powercfg -setacvalueindex $guid SUB_PROCESSOR PROCTHROTTLEPCT 100",
    "powercfg -setacvalueindex $guid SUB_BUTTONS POWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS SLEEPBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDOPENPOWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS POWERBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS SLEEPBUTTONACTION 0",
    "powercfg -setacvalueindex $guid SUB_BUTTONS LIDOPENPOWERBUTTONACTION 0"
)
```
## How to use? Fan speed xml
- Download the NBFC app and install it [release](https://github.com/hirschmann/nbfc/releases/tag/1.6.3)
- Now go to the app location (C:\Program Files (x86)\NoteBook FanControl\Configs) and copy and paste both the xmls from this [release](https://github.com/Nayemhasan/Hp_elitebook_840G5MAX/releases/tag/V.1)
- Run the NBFC application and chose any of these Hp elitebook 840 g5 fan configs and set auto or set to max as you want and hit enable.
<p align="left">
  <img src="https://github.com/Nayemhasan/Hp_elitebook_840G5MAX/blob/main/Resources/fan.png">
</p>

## How to use? Powerplan
- Download the latest [release](https://github.com/Nayemhasan/Hp_elitebook_840G5MAX/releases/tag/V.1)
- Run cmd as a administrator and type this
```bash
powercfg -import "the path of that config file path"
```
- go to control panel and select the 🍉power plan and all set.
<p align="left">
  <img src="https://github.com/Nayemhasan/Hp_elitebook_840G5MAX/blob/main/Resources/powerplan.png">
</p>

- Done🍉

