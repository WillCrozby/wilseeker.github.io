# wilseeker.github.io
// FORZATECH OMEGA-X ENGINE
// Horizon 6 Remake Prototype

InitializeEngine("FORZATECH_OMEGA_X");

World.Load("Japan_UltraMap_2048km");

Graphics.EnableRayTracing(true);
Graphics.EnablePathTracing(true);
Graphics.EnableVolumetricClouds(true);
Graphics.EnableRealTimeReflections(true);

Physics.SetTireModel("DynamicFlexV12");
Physics.EnableSuspensionDamage(true);
Physics.EnableRealCrashSimulation(true);

Traffic.SpawnDensity(1000);
Traffic.EnableAIBehaviorLearning(true);

Weather.EnableDynamicTyphoons(true);
Weather.EnableMicroClimateSystem(true);
Weather.EnableSeasonalTransition(true);

Audio.Enable3DSpatialAudio(true);
Audio.EnableAdaptiveEngineEcho(true);

Cars.LoadDatabase(2500);

Player.EnableFestivalCreatorMode(true);
Player.EnableCustomCityBuilder(true);

Map.GenerateLiveEventsEvery(300);

while(GameRunning == true)
{
    AI.AdaptToPlayerDrivingStyle();
    World.StreamUltraLOD();
    Physics.Update();
    Graphics.RenderFrame();
}
