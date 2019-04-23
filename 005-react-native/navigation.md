# navigation



1. createSwitchNavigator

   화면 전환. 기존의 web route와 동일하게 화면을 이동 

   this.props.navigation.navigate('Test') 사용 

2. createStackNavigator

   this.props.navigation.navigate('Test') 사용으로 헤더에 <- ( back ) 버튼이 생기는 child route로 이동 



3. createDrawerNavigator

   this.props.navigation.openDrawer() -> 좌측 drawer를 오픈

   this.props.navigation.closeDrawer() -> drawer를 닫

   this.props.navigation.toggleDrawer() -> 토글



   this.props.navigation.dispatch(DrawerActions.openDrawer());
   this.props.navigation.dispatch(DrawerActions.closeDrawer());
   this.props.navigation.dispatch(DrawerActions.toggleDrawer());
