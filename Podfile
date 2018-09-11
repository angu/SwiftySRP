# TODO: Bump this up to iOS9
workspace 'SwiftySRP'

abstract_target 'SwiftySRP_Base' do
    use_frameworks!
    
	pod 'BigInt', :git => 'https://github.com/lorentey/BigInt.git', :tag => 'v3.0.0'
    pod 'FFDataWrapper', :git => 'https://github.com/flockoffiles/FFDataWrapper.git', :tag => 'v1.2'
    
    target 'SwiftySRP' do
	  platform :ios, '9.0'
      project 'SwiftySRP'
	  
      
      target 'SwiftySRPTests' do
      end
    end
	
    target 'SwiftySRP-macOS' do
	  platform :osx, '10.13'
      project 'SwiftySRP'
    end

    target 'SwiftySRPTestApp' do
		platform :ios, '9.0'
        project 'SwiftySRPTestApp'
        pod 'SwiftySRP', :path => './SwiftySRP.podspec'

        target 'SwiftySRPTestAppTests' do
        end
        
    end

    target 'SwiftySRPPlayground' do
  	  platform :ios, '9.0'
      project 'SwiftySRPPlayground'
      pod 'SwiftySRP', :path => './SwiftySRP.podspec'
    end
    
end

# This part is essential for playgrounds to work properly with frameworks installed with cocoapods.
post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['SWIFT_VERSION'] = '4.0'
            config.build_settings['CONFIGURATION_BUILD_DIR'] = '$PODS_CONFIGURATION_BUILD_DIR'
            if config.name == 'Debug'
                config.build_settings['OTHER_SWIFT_FLAGS'] = '-DDEBUG'
                else
                config.build_settings['OTHER_SWIFT_FLAGS'] = ''
            end
        end
    end
end
