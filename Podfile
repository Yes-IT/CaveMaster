#platform :ios, '12.0'

#inhibit_all_warnings!
#install! 'cocoapods', :warn_for_unused_master_specs_repo => false

def all_pods
  
  pod 'SwifterSwift'
  pod 'IQKeyboardManager'
  pod 'SwiftyJSON'
  pod 'KeychainAccess'
  pod 'SwiftMessages'
  pod 'ActionSheetPicker-3.0'
  pod 'Firebase/Crashlytics'
  pod 'Firebase/Analytics'
  pod 'UIScrollView-InfiniteScroll'
  pod 'DeviceLayout'
  pod 'GoogleSignIn'
  pod 'DeviceLayout'
  pod 'GrowingTextView'
  pod 'InputMask'
  pod 'PanModal'
  pod 'Nine41'
  pod 'Nuke'
  pod "BSImagePicker"
  pod 'Firebase/Core'
  pod 'Firebase/Auth'
  pod 'Firebase/Firestore'
  pod 'Firebase/Functions'
  pod 'Firebase/Storage'
  pod 'Firebase/Messaging'
  pod 'Firebase/Analytics'

end

target 'cave' do
  use_frameworks!
  all_pods
end


post_install do |installer|
  installer.pods_project.build_configurations.each do |config|
    config.build_settings.delete('CODE_SIGNING_ALLOWED')
    config.build_settings.delete('CODE_SIGNING_REQUIRED')
    config.build_settings['LD_NO_PIE'] = 'NO'
  end
  
  installer.pods_project.build_configurations.each do |config|
    next unless config.name == 'Debug'
    
    config.build_settings['LD_RUNPATH_SEARCH_PATHS'] = [
    '$(FRAMEWORK_SEARCH_PATHS)'
    ]
  end
  
  installer.pods_project.targets.each do |t|
    t.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '12.0'
    end
  end
end
