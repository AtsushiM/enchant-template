//init enchant.js
enchant();

var XXX = (function(win, doc) {
    //hidden url bar
    (function() {
        var doScroll = function() {
            if (win.pageYOffset === 0) {
                win.scrollTo(0, 1);
            }
        };
        win.onorientationchange = function() {
            setTimeout(doScroll, 100);
        };
        win.addEventListener('load', win.onorientationchange, false);
    }());

    var Public = {}, //Public methods
        CONST = { //Constant Vals
            game: {
                width: 320,
                height: 320
            },
            map: {
                image: 'img/map.png',
                chip: {
                    width: 32,
                    height: 32
                }
            },
            unit: {
                image: 'img/unit.png',
                chip: {
                    width: 16,
                    height: 16
                }
            },
            effect: {
                image: 'img/effect.png',
                chip: {
                    width: 16,
                    height: 16
                }
            },
            group: {
                // group config
                unit: new Group(),
                effect: new Group()
            },
            sound: {
                //add sound.
                bgm: 'sound/bgm.mp3'
            }
        },
        GAME = new Game(CONST.game.width, CONST.game.height),
        ROOT = GAME.rootScene,
        MAP,
        SOUND = {};

    //prelaod
    GAME.preload([
        //add files
        CONST.map.image,
        CONST.unit.image,
        CONST.effect.image,
        CONST.sound.bgm
    ]);

    //Game loaded action
    GAME.onload = function() {
        //make map
        MAP = new Map(CONST.map.chip.width, CONST.map.chip.height);
        MAP.image = GAME.assets[CONST.map.image];
        MAP.loadData([
            //map data(array)
            [0, 1, 2, 3, 4, 5],
            [0, 1, 2, 3, 4, 5],
            [0, 1, 2, 3, 4, 5]
        ]);

        //set layer
        ROOT.addChild(MAP);
        ROOT.addChild(CONST.group.unit);
        ROOT.addChild(CONST.group.effect);

        SOUND.bgm = GAME.assets[CONST.sound.bgm];

        //add your code.
    };

    //Game start
    GAME.start();

    return Public;
}(this, this.document));
