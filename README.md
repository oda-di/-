Заспавнить золотой дигл 

subclass_create weapon_deagle_prefab {"classname" "weapon_awp" "rendercolor" "255 215 0"}

/////////////////////////

На карте спавнится 100 куриц

sv_minimum_desired_chicken_count 100

/////////////////////////

Коробки которые невозможно удалить

ent_create func_brush {"model" "models/props/de_train/hr_t/train_cratestack/train_cratestack.vmdl"}

/////////////////////////////////////////////////////////////

Заспавнить капкан (может быть только один за раунд)

ent_create prop_dynamic  {"model" "models/weapons/w_eq_beartrap_dropped.vmdl" "targetname" "prop_beartrap"};
ent_create func_bomb_target {"model" "models/props/de_dust/hr_dust/dust_soccerball/dust_soccer_ball001.vmdl" "isenabled" "1" "targetname" "func_beartrap"};
ent_fire func_beartrap addoutput OnStartTouch>!activator>sethealth>-1>0>0 1;
ent_fire func_beartrap addoutput OnStartTouch>prop_beartrap>setanimation>close>0>0 1;
ent_fire func_beartrap addoutput OnStartTouch>!caller>kill>0>0>0 1;
ent_create ambient_generic {"targetname" "beartrap_prepare" "message" "radio_computer.break" "radius" "1250" "volstart" "10" "spawnflags" "33" "preset" "27"};
ent_fire func_beartrap addoutput "OnStartTouch>beartrap_prepare>playsound>0>0>0" 1;
ent_fire func_beartrap addoutput "OnStartTouch>beartrap_prepare>kill>0>2>0" 1;
ent_fire func_beartrap addoutput "OnStartTouch>prop_beartrap>kill>0>2>0" 1;

/////////////////////////

Команда на спавн конвеера

ent_create func_conveyor {"model" "models/ar_baggage/conveyor/conveyor_belt_01_078.vmdl" "speed" "1000" "movedir" "-180 -360 180"}

/////////////////////////

Команда на спавн бомбы.

plant_bomb

/////////////////////////

Команда на удаление бомбы

clear_bombs

/////////////////////////

Спавнит фонарик

dlight_debug

/////////////////////////

Бомба взрывает всю карту

map_setbombradius 9999

/////////////////////////

Получать 1 урон каждую секунду

mp_global_damage_per_second 1

/////////////////////////

Команда чтоб взаимодействовать на большой дистанции (по умолчанию 80)

player_use_radius 9999

/////////////////////////

Трупы смешно отлетают после смерти (по умолчанию 1)

ragdoll_gravity_scale 0.1

/////////////////////////

Игрок скользит по земле, как по льду (по умолчанию 5.2)

sv_friction 1

/////////////////////////

Игрок моментально регенерируется

sv_regeneration_force_on 1

/////////////////////////

Команда на бакшот-рулетку. Прописать, когда смотришь на какую-то поверхность

mp_autokick 0;
sv_cheats 1;
mp_death_drop_gun 1;
ent_create prop_door_rotating {"model" "models/props/de_vertigo/trafficcone_clean.vmdl" "targetname" "dor" "spawnflags" "2048" "scale" "0"};
ent_create weapon_nova {"targetname" "weapon_nova" "CanBePickedUp" "0" "scale" "0" "rendercolor" "255 200 200"};
ent_create logic_case {"targetname" "case"};
ent_create ambient_generic {"targetname" "sound_prepare" "message" "Weapon_Nova.Pump" "radius" "1250" "volstart" "10" "spawnflags" "33" "preset" "27"};
ent_create ambient_generic {"targetname" "sound_shot" "message" "Weapon_Nova.Single" "radius" "1250" "volstart" "10" "spawnflags" "33" "preset" "27"};
ent_create ambient_generic {"targetname" "sound_roll" "message" "Weapon_Nova.Draw" "radius" "1250" "volstart" "10" "spawnflags" "33" "preset" "27"};
ent_create ambient_generic {"targetname" "sound_mt" "message" "Default.ClipEmpty_Rifle" "radius" "1250" "volstart" "10" "spawnflags" "33" "preset" "27"};
ent_fire !player addoutput OnUser4>sound_mt>followentity>weapon_nova>0>0 1;
ent_fire !player addoutput OnUser4>sound_prepare>followentity>weapon_nova>0>0 1;
ent_fire !player addoutput OnUser4>sound_shot>followentity>weapon_nova>0>0 1;
ent_fire !player addoutput OnUser4>sound_roll>followentity>weapon_nova>0>0 1;
ent_fire !player fireuser4:2;
ent_fire weapon_nova addoutput "OnUser1>!activator>sethealth>0>1.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>sound_prepare>playsound>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser1>sound_shot>playsound>0>1.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>weapon_nova>followentity>dor>0>0" 1;
ent_fire weapon_nova addoutput "OnUser1>weapon_nova>followentity>>1.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>dor>unlock>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser1>dor>use>0>0.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>dor>lock>0>1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>kanye>start>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser1>kanye>stop>0>0.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>kanye2>start>0>1.1>0" 1;
ent_fire weapon_nova addoutput "OnUser1>kanye2>stop>0>2>0" 1;
ent_fire weapon_nova addoutput OnUser3>weapon_nova>followentity>dor>0.3>0 1;
ent_fire weapon_nova addoutput OnUser3>weapon_nova>followentity>>0.4>0 1;
ent_fire weapon_nova addoutput OnUser3>weapon_nova>setscale>1>0.4>0 1;
ent_fire weapon_nova addoutput OnUser3>dor>setscale>1>0.35>0 1;
ent_fire weapon_nova addoutput OnUser3>kanye>followentity>dor>0.2>0 1;
ent_fire weapon_nova addoutput OnUser3>kanye2>followentity>dor>0.2>0 1;
ent_fire weapon_nova addoutput "OnUser2>sound_prepare>playsound>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser2>sound_mt>playsound>0>1.1>0" 1;
ent_fire weapon_nova addoutput "OnUser2>dor>unlock>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser2>dor>use>0>0.1>0" 1;
ent_fire weapon_nova addoutput "OnUser2>dor>lock>0>1>0" 1;
ent_fire weapon_nova addoutput "OnUser2>weapon_nova>followentity>dor>0>0" 1;
ent_fire weapon_nova addoutput "OnUser2>weapon_nova>followentity>>2>0" 1;
ent_fire weapon_nova addoutput "OnUser2>kanye>start>0>0>0" 1;
ent_fire weapon_nova addoutput "OnUser2>kanye>stop>0>0.1>0" 1;
ent_fire sound_roll playsound:1;
ent_fire case addoutput "OnCase01>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase02>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase03>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase04>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase05>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase06>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase07>weapon_nova>fireuser2>0>0>0" 1;
ent_fire case addoutput "OnCase08>weapon_nova>fireuser1>0>0>0" 1;
ent_fire weapon_nova addoutput OnPlayeruse>case>pickrandomshuffle>0>0>0 1;
ent_fire dor disablecollision:1;
ent_fire dor alpha 0 1;
ent_fire weapon_nova fireuser3:1;
ent_create env_particle_glow {"effect_textureOverride" "materials\models\weapons\shared\shells\shells_color_tga_748fe611.vtex" "targetname" "kanye" "effect_name" "particles/weapons/cs_weapon_fx/weapon_shell_casing_shotgun.vpcf"};
ent_create env_particle_glow {"effect_textureOverride" "materials/particle/fire_particle_3/fire_particle_3.vtex" "targetname" "kanye2" "effect_name" "particles/inferno_fx/explosion_incend_air_fallingfire.vpcf"};


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Команда на дефьюз бомбы за 0.000 до взрыва. Прописывать, когда игрешь за КТ.

sv_cheats 1;
mp_anyone_can_pickup_c4 1; 
give weapon_c4; 
ent_create point_servercommand {"targetname" "point_servercomman"};
ent_fire point_servercommand addoutput "classname func_brush";
ent_fire func_bomb_target addoutput BombPlanted>point_servercomman>command>+use>34.98>0 1;
ent_fire func_bomb_target addoutput BombPlanted>point_servercomman>command>-use>40>0 1;

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Команда, чтоб хаешки становились супер-большими, когда ударяются об стену.

sv_cheats 1;
ent_create logic_eventlistener {"EventName" "grenade_bounce" "isEnabled" "1" "targetname" "game_3"};
sv_infinite_ammo 1;
sv_hegrenade_damage_multiplier 2;
ent_create point_servercommand;
ent_fire !player addoutput OnUser3>point_servercommand>command>grenkis>0>0;
alias grenkis "ent_fire game_3 addoutput OnEventFired>hegrenade_projectile>setscale>10>0>0";
ent_fire !player fireuser3:1;

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Команда на спавн бета-макета второго даста. Прописывать, когда играешь на dust2

sv_cheats 1;
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_center.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_kasbah1.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_kasbah2.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_kasbah3.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_market1.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_market3.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_urban2.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_urban3.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_urban4.vmdl" "angles" "180 0 180" "origin" "0 0 0"};
ent_create prop_dynamic {"model" "models\props\de_dust\hr_dust\s2_reference_geo\s2_reference_urban5.vmdl" "angles" "180 0 180" "origin" "0 0 0"}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Куб, который можно перетаскивать, с помощью команды (ent_grab -toggle)

ent_create func_pushable {"model" "models\de_inferno\stone_wall_09\cube_test.vmdl"}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
