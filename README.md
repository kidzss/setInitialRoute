Use initWithEngine:nibName:bundle: method to create FlutterViewController, and then setInitialRoute not working 

I solved the problem.
//=======================

@interface XXFlutterViewController : FlutterViewController

@EnD

(void)viewDidLoad {
[super viewDidLoad];
// Do any additional setup after loading the view.
FlutterEngine *flutterEngine = self.engine;

[GeneratedPluginRegistrant registerWithRegistry:flutterEngine];
//custom futter plugin
[XXXFlutterBridge registerWithRegistry:flutterEngine];
}

//open flutter vc
XXFlutterViewController *flutterViewController = [[XXFlutterViewController alloc] init];
[flutterViewController setInitialRoute:@"xxxxx/xxxx"];
