# Hp_elitebook_840G5MAX
Max fan speed with custom power plan to get max performance from HP ELITEBOOK 840 G5
## Aout the fan xml
- fan xml stripped form the latest bios
- adjusted Ec Poll Interval to 100ms to better cool off the cpu
- auto mode kick in faster than stock to max speed
- idle to max temp range with mod 35°-70°C
## About the powerplan
- maxed out everything even on battery power mode too *enable dc turbo boost from bios
- process states maxed out to 100% for no reason*

`Fan xml to the max`
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
