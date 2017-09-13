<?xml version="1.0" encoding="UTF-8"?>
<jmeterTestPlan version="1.2" properties="3.2" jmeter="3.2 r1790748">
  <hashTree>
    <TestPlan guiclass="TestPlanGui" testclass="TestPlan" testname="Test Plan" enabled="true">
      <stringProp name="TestPlan.comments"></stringProp>
      <boolProp name="TestPlan.functional_mode">false</boolProp>
      <boolProp name="TestPlan.serialize_threadgroups">false</boolProp>
      <elementProp name="TestPlan.user_defined_variables" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" testname="User Defined Variables" enabled="true">
        <collectionProp name="Arguments.arguments"/>
      </elementProp>
      <stringProp name="TestPlan.user_define_classpath"></stringProp>
    </TestPlan>
    <hashTree>
      <Arguments guiclass="ArgumentsPanel" testclass="Arguments" testname="User Defined Variables" enabled="true">
        <collectionProp name="Arguments.arguments"/>
      </Arguments>
      <hashTree/>
      <ConfigTestElement guiclass="HttpDefaultsGui" testclass="ConfigTestElement" testname="HTTP Request Defaults" enabled="true">
        <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables" enabled="true">
          <collectionProp name="Arguments.arguments"/>
        </elementProp>
        <stringProp name="HTTPSampler.domain"></stringProp>
        <stringProp name="HTTPSampler.port"></stringProp>
        <stringProp name="HTTPSampler.protocol"></stringProp>
        <stringProp name="HTTPSampler.contentEncoding"></stringProp>
        <stringProp name="HTTPSampler.path"></stringProp>
        <stringProp name="HTTPSampler.concurrentPool">6</stringProp>
        <stringProp name="HTTPSampler.connect_timeout"></stringProp>
        <stringProp name="HTTPSampler.response_timeout"></stringProp>
      </ConfigTestElement>
      <hashTree/>
      <CookieManager guiclass="CookiePanel" testclass="CookieManager" testname="HTTP Cookie Manager" enabled="true">
        <collectionProp name="CookieManager.cookies"/>
        <boolProp name="CookieManager.clearEachIteration">false</boolProp>
        <stringProp name="CookieManager.policy">standard</stringProp>
        <stringProp name="CookieManager.implementation">org.apache.jmeter.protocol.http.control.HC4CookieHandler</stringProp>
      </CookieManager>
      <hashTree/>
      <ThreadGroup guiclass="ThreadGroupGui" testclass="ThreadGroup" testname="Thread Group" enabled="true">
        <stringProp name="ThreadGroup.on_sample_error">continue</stringProp>
        <elementProp name="ThreadGroup.main_controller" elementType="LoopController" guiclass="LoopControlPanel" testclass="LoopController" testname="Loop Controller" enabled="true">
          <boolProp name="LoopController.continue_forever">false</boolProp>
          <intProp name="LoopController.loops">-1</intProp>
        </elementProp>
        <stringProp name="ThreadGroup.num_threads">1</stringProp>
        <stringProp name="ThreadGroup.ramp_time">1</stringProp>
        <longProp name="ThreadGroup.start_time">1370726934000</longProp>
        <longProp name="ThreadGroup.end_time">1370726934000</longProp>
        <boolProp name="ThreadGroup.scheduler">false</boolProp>
        <stringProp name="ThreadGroup.duration"></stringProp>
        <stringProp name="ThreadGroup.delay"></stringProp>
      </ThreadGroup>
      <hashTree>
        <RecordingController guiclass="RecordController" testclass="RecordingController" testname="Recording Controller" enabled="true"/>
        <hashTree>
          <TransactionController guiclass="TransactionControllerGui" testclass="TransactionController" testname="/empower/sessions" enabled="true">
            <boolProp name="TransactionController.includeTimers">false</boolProp>
            <boolProp name="TransactionController.parent">false</boolProp>
          </TransactionController>
          <hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/empower/sessions" enabled="true">
              <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">{&quot;RememberMe&quot;:false,&quot;TwoFactorAuthCookie&quot;:&quot;&quot;,&quot;culture&quot;:&quot;en-US&quot;,&quot;isStaffLogin&quot;:false}</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/empower/sessions</stringProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/login/patient?returnUrl=%2F</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Content-Type" elementType="Header">
                    <stringProp name="Header.name">Content-Type</stringProp>
                    <stringProp name="Header.value">application/json;charset=utf-8</stringProp>
                  </elementProp>
                  <elementProp name="Portal" elementType="Header">
                    <stringProp name="Header.name">Portal</stringProp>
                    <stringProp name="Header.value">null</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
              <JSONPostProcessor guiclass="JSONPostProcessorGui" testclass="JSONPostProcessor" testname="JSON Extractor" enabled="true">
                <stringProp name="JSONPostProcessor.referenceNames">token</stringProp>
                <stringProp name="JSONPostProcessor.jsonPathExprs">$..sessionId</stringProp>
                <stringProp name="JSONPostProcessor.match_numbers">1</stringProp>
              </JSONPostProcessor>
              <hashTree/>
              <JSONPostProcessor guiclass="JSONPostProcessorGui" testclass="JSONPostProcessor" testname="JSON Extractor" enabled="true">
                <stringProp name="JSONPostProcessor.referenceNames">userID</stringProp>
                <stringProp name="JSONPostProcessor.jsonPathExprs">$..userId</stringProp>
                <stringProp name="JSONPostProcessor.match_numbers">1</stringProp>
              </JSONPostProcessor>
              <hashTree/>
              <JSONPostProcessor guiclass="JSONPostProcessorGui" testclass="JSONPostProcessor" testname="JSON Extractor" enabled="true">
                <stringProp name="JSONPostProcessor.referenceNames">patientID</stringProp>
                <stringProp name="JSONPostProcessor.jsonPathExprs">$..PatientId</stringProp>
                <stringProp name="JSONPostProcessor.match_numbers">1</stringProp>
              </JSONPostProcessor>
              <hashTree/>
              <JSONPostProcessor guiclass="JSONPostProcessorGui" testclass="JSONPostProcessor" testname="JSON Extractor" enabled="true">
                <stringProp name="JSONPostProcessor.referenceNames">MID</stringProp>
                <stringProp name="JSONPostProcessor.jsonPathExprs">$..MedseekId</stringProp>
                <stringProp name="JSONPostProcessor.match_numbers">1</stringProp>
              </JSONPostProcessor>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/users/current/permission-set" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/users/current/permission-set</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/login/patient?returnUrl=%2F</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/users/{userID}/profile" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/users/${userID}/profile</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/login/patient?returnUrl=%2F</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/users/{userID}/current-patient" enabled="true">
              <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">{&quot;patient&quot;:{&quot;id&quot;:${patientID}}}</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/users/${userID}/current-patient</stringProp>
              <stringProp name="HTTPSampler.method">PUT</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/?returnUrl=%2F</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Content-Type" elementType="Header">
                    <stringProp name="Header.name">Content-Type</stringProp>
                    <stringProp name="Header.value">application/json;charset=utf-8</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/notificationCenter/notifications" enabled="true">
              <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">{&quot;userId&quot;:${userID},&quot;medseekPatientId&quot;:&quot;&quot;,&quot;status&quot;:&quot;UnRead&quot;}</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/notificationCenter/notifications</stringProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Content-Type" elementType="Header">
                    <stringProp name="Header.name">Content-Type</stringProp>
                    <stringProp name="Header.value">application/json;charset=utf-8</stringProp>
                  </elementProp>
                  <elementProp name="Portal" elementType="Header">
                    <stringProp name="Header.name">Portal</stringProp>
                    <stringProp name="Header.value">null</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/empower/patients/{patientID}/profile-image" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/empower/patients/${patientID}/profile-image</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">If-Modified-Since</stringProp>
                    <stringProp name="Header.value">Thu, 01 Jan 1970 00:00:00 GMT</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Cache-Control</stringProp>
                    <stringProp name="Header.value">no-cache</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/notificationCenterInformation" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/notificationCenterInformation</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Cache-Control</stringProp>
                    <stringProp name="Header.value">no-cache</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/notificationCenter/notifications" enabled="true">
              <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">{&quot;userId&quot;:${userID},&quot;medseekPatientId&quot;:&quot;${MID}&quot;,&quot;status&quot;:&quot;UnRead&quot;}</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/notificationCenter/notifications</stringProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Content-Type" elementType="Header">
                    <stringProp name="Header.name">Content-Type</stringProp>
                    <stringProp name="Header.value">application/json;charset=utf-8</stringProp>
                  </elementProp>
                  <elementProp name="Portal" elementType="Header">
                    <stringProp name="Header.name">Portal</stringProp>
                    <stringProp name="Header.value">null</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/modules/Mhr/settings" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/modules/Mhr/settings</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/modules/AppointmentRequest/settings" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/modules/AppointmentRequest/settings</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/users/{userID}/image" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/users/${userID}/image</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Host</stringProp>
                    <stringProp name="Header.value">dev-patient.hosting.influencehealth.com</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Cache-Control</stringProp>
                    <stringProp name="Header.value">no-cache</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">If-Modified-Since</stringProp>
                    <stringProp name="Header.value">Thu, 01 Jan 1970 00:00:00 GMT</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Pragma</stringProp>
                    <stringProp name="Header.value">no-cache</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Host</stringProp>
                    <stringProp name="Header.value">${__P(API)}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/empower/patients/requests/pending" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="limit" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">limit</stringProp>
                    <stringProp name="Argument.value">5</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="offset" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">offset</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">Descending</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortField" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortField</stringProp>
                    <stringProp name="Argument.value">LastUpdatedDate</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/empower/patients/requests/pending</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/modules/Mhr/settings" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/modules/Mhr/settings</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/empower/patients/{patientID}/appointments/future" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="mid" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">mid</stringProp>
                    <stringProp name="Argument.value">5d0a0fbb-1d4d-4608-be43-d60a22d0eb45</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="directOnly" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">directOnly</stringProp>
                    <stringProp name="Argument.value">false</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/empower/patients/${patientID}/appointments/future</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/empower/audit-log/users/{userID}" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageNumber" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageNumber</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="startDate" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">startDate</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="endDate" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">endDate</stringProp>
                    <stringProp name="Argument.value"></stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/empower/audit-log/users/${userID}</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/medications" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">startDate</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/medications</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/procedures" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/procedures</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/family-history" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">onsetDate</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/family-history</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/problems" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/problems</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/allergies" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">startDate</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/allergies</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/social-history" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">yearStarted</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/social-history</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/notificationCenter/notifications" enabled="true">
              <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">{&quot;userId&quot;:${userID},&quot;medseekPatientId&quot;:&quot;${MID}&quot;,&quot;status&quot;:&quot;UnRead&quot;}</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
              <stringProp name="HTTPSampler.path">/notificationCenter/notifications</stringProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Content-Type" elementType="Header">
                    <stringProp name="Header.name">Content-Type</stringProp>
                    <stringProp name="Header.value">application/json;charset=utf-8</stringProp>
                  </elementProp>
                  <elementProp name="Portal" elementType="Header">
                    <stringProp name="Header.name">Portal</stringProp>
                    <stringProp name="Header.value">null</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/immunizations" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/immunizations</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/weights" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/weights</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/blood-glucoses" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/blood-glucoses</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/blood-pressures" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/blood-pressures</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/test-results" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/test-results</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/clinical-documents" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/clinical-documents</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="/v2/patients/{patientID}/cholesterols" enabled="true">
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="page" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">page</stringProp>
                    <stringProp name="Argument.value">1</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="pageSize" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">pageSize</stringProp>
                    <stringProp name="Argument.value">20</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortBy" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortBy</stringProp>
                    <stringProp name="Argument.value">date</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                  <elementProp name="sortDirection" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.name">sortDirection</stringProp>
                    <stringProp name="Argument.value">desc</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
              <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
              <stringProp name="HTTPSampler.port">443</stringProp>
              <stringProp name="HTTPSampler.protocol">https</stringProp>
              <stringProp name="HTTPSampler.contentEncoding"></stringProp>
              <stringProp name="HTTPSampler.path">/v2/patients/${patientID}/cholesterols</stringProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
              <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
              <stringProp name="HTTPSampler.connect_timeout"></stringProp>
              <stringProp name="HTTPSampler.response_timeout"></stringProp>
            </HTTPSamplerProxy>
            <hashTree>
              <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
                <collectionProp name="HeaderManager.headers">
                  <elementProp name="Referer" elementType="Header">
                    <stringProp name="Header.name">Referer</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}/</stringProp>
                  </elementProp>
                  <elementProp name="clientTenantId" elementType="Header">
                    <stringProp name="Header.name">clientTenantId</stringProp>
                    <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                  </elementProp>
                  <elementProp name="portalGroup" elementType="Header">
                    <stringProp name="Header.name">portalGroup</stringProp>
                    <stringProp name="Header.value">PortalGroup7063025</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Language" elementType="Header">
                    <stringProp name="Header.name">Accept-Language</stringProp>
                    <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                  </elementProp>
                  <elementProp name="Origin" elementType="Header">
                    <stringProp name="Header.name">Origin</stringProp>
                    <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                  </elementProp>
                  <elementProp name="DNT" elementType="Header">
                    <stringProp name="Header.name">DNT</stringProp>
                    <stringProp name="Header.value">1</stringProp>
                  </elementProp>
                  <elementProp name="Accept" elementType="Header">
                    <stringProp name="Header.name">Accept</stringProp>
                    <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                  </elementProp>
                  <elementProp name="preferredLanguage" elementType="Header">
                    <stringProp name="Header.name">preferredLanguage</stringProp>
                    <stringProp name="Header.value">en-US</stringProp>
                  </elementProp>
                  <elementProp name="Accept-Encoding" elementType="Header">
                    <stringProp name="Header.name">Accept-Encoding</stringProp>
                    <stringProp name="Header.value">gzip, deflate, br</stringProp>
                  </elementProp>
                  <elementProp name="User-Agent" elementType="Header">
                    <stringProp name="Header.name">User-Agent</stringProp>
                    <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0</stringProp>
                  </elementProp>
                  <elementProp name="" elementType="Header">
                    <stringProp name="Header.name">Authorization</stringProp>
                    <stringProp name="Header.value">Bearer ${token}</stringProp>
                  </elementProp>
                </collectionProp>
              </HeaderManager>
              <hashTree/>
            </hashTree>
          </hashTree>
          <AuthManager guiclass="AuthPanel" testclass="AuthManager" testname="HTTP Authorization Manager" enabled="true">
            <collectionProp name="AuthManager.auth_list">
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/sessions</stringProp>
                <stringProp name="Authorization.username">${__P(username)}</stringProp>
                <stringProp name="Authorization.password">${__P(password)}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/current/permission-set</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/${userID}/profile</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(patientURL)}/themes/default/images/patterns/svg-patterns.svg</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/targetGroups/${userID}/campaigns</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/dynamicTexts/NotificationCenter/dynamicText</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/${userID}/current-patient</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/notificationCenter/${userID}/5d0a0fbb-1d4d-4608-be43-d60a22d0eb45</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/modules/profile/settings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/messages/messagecenter/settings/modulesettings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/${userID}/settings/timezone</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/message-center/mailboxes/inbox/messages/count?unread=true</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/settings/landingpage/landingPageTourSetings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/notificationCenter/notifications</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/patients/0/appointments/dynamic-text</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/patients/${patientID}/profile-image</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/notificationCenterInformation</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/settings/patient/${userID}/landingPageTileSettings?key=MedSeek.Portal.Module.LandingPage.Settings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/modules/Mhr/settings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/modules/AppointmentRequest/settings</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/${userID}/image</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/users/current/landing-page/tiles</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/patients/requests/pending?limit=5&amp;offset=1&amp;sortDirection=Descending&amp;sortField=LastUpdatedDate</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/patients/${patientID}/appointments/future?mid=5d0a0fbb-1d4d-4608-be43-d60a22d0eb45&amp;directOnly=false</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/empower/audit-log/users/${userID}?pageSize=&amp;pageNumber=&amp;sortBy=&amp;sortDirection=&amp;startDate=&amp;endDate=</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/medications?page=1&amp;pageSize=20&amp;sortBy=startDate&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/procedures?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/family-history?page=1&amp;pageSize=20&amp;sortBy=onsetDate&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/problems?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/allergies?page=1&amp;pageSize=20&amp;sortBy=startDate&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/social-history?page=1&amp;pageSize=20&amp;sortBy=yearStarted&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/immunizations?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/weights?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/blood-glucoses?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/blood-pressures?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/test-results?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/clinical-documents?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
              <elementProp name="" elementType="Authorization">
                <stringProp name="Authorization.url">https://${__P(API)}/v2/patients/${patientID}/cholesterols?page=1&amp;pageSize=20&amp;sortBy=date&amp;sortDirection=desc</stringProp>
                <stringProp name="Authorization.username">${AUTH_LOGIN}</stringProp>
                <stringProp name="Authorization.password">${AUTH_PASSWORD}</stringProp>
                <stringProp name="Authorization.domain"></stringProp>
                <stringProp name="Authorization.realm"></stringProp>
                <stringProp name="Authorization.mechanism">KERBEROS</stringProp>
              </elementProp>
            </collectionProp>
            <boolProp name="AuthManager.clearEachIteration">true</boolProp>
          </AuthManager>
          <hashTree/>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="DELETE /empower/sessions/{userID}" enabled="true">
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" enabled="true">
              <collectionProp name="Arguments.arguments"/>
            </elementProp>
            <stringProp name="HTTPSampler.domain">${__P(API)}</stringProp>
            <stringProp name="HTTPSampler.port">443</stringProp>
            <stringProp name="HTTPSampler.protocol">https</stringProp>
            <stringProp name="HTTPSampler.contentEncoding"></stringProp>
            <stringProp name="HTTPSampler.path">/empower/sessions/${userID}</stringProp>
            <stringProp name="HTTPSampler.method">DELETE</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
            <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
            <stringProp name="HTTPSampler.connect_timeout"></stringProp>
            <stringProp name="HTTPSampler.response_timeout"></stringProp>
          </HTTPSamplerProxy>
          <hashTree>
            <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP Header Manager" enabled="true">
              <collectionProp name="HeaderManager.headers">
                <elementProp name="clientTenantId" elementType="Header">
                  <stringProp name="Header.name">clientTenantId</stringProp>
                  <stringProp name="Header.value">DevClient:Empower:DevPG:Optional</stringProp>
                </elementProp>
                <elementProp name="Referer" elementType="Header">
                  <stringProp name="Header.name">Referer</stringProp>
                  <stringProp name="Header.value">https://${__P(patientURL)}/?p=null</stringProp>
                </elementProp>
                <elementProp name="portalGroup" elementType="Header">
                  <stringProp name="Header.name">portalGroup</stringProp>
                  <stringProp name="Header.value">PortalGroup7063025</stringProp>
                </elementProp>
                <elementProp name="Accept-Language" elementType="Header">
                  <stringProp name="Header.name">Accept-Language</stringProp>
                  <stringProp name="Header.value">en-US,en;q=0.5</stringProp>
                </elementProp>
                <elementProp name="Origin" elementType="Header">
                  <stringProp name="Header.name">Origin</stringProp>
                  <stringProp name="Header.value">https://${__P(patientURL)}</stringProp>
                </elementProp>
                <elementProp name="Accept" elementType="Header">
                  <stringProp name="Header.name">Accept</stringProp>
                  <stringProp name="Header.value">application/json, text/plain, */*</stringProp>
                </elementProp>
                <elementProp name="preferredLanguage" elementType="Header">
                  <stringProp name="Header.name">preferredLanguage</stringProp>
                  <stringProp name="Header.value">en-US</stringProp>
                </elementProp>
                <elementProp name="Accept-Encoding" elementType="Header">
                  <stringProp name="Header.name">Accept-Encoding</stringProp>
                  <stringProp name="Header.value">gzip, deflate, br</stringProp>
                </elementProp>
                <elementProp name="User-Agent" elementType="Header">
                  <stringProp name="Header.name">User-Agent</stringProp>
                  <stringProp name="Header.value">Mozilla/5.0 (Windows NT 10.0; WOW64; rv:55.0) Gecko/20100101 Firefox/55.0</stringProp>
                </elementProp>
                <elementProp name="" elementType="Header">
                  <stringProp name="Header.name">Authorization</stringProp>
                  <stringProp name="Header.value">Bearer ${token}</stringProp>
                </elementProp>
              </collectionProp>
            </HeaderManager>
            <hashTree/>
          </hashTree>
        </hashTree>
      </hashTree>
      <Summariser guiclass="SummariserGui" testclass="Summariser" testname="Generate Summary Results" enabled="true"/>
      <hashTree/>
      <BackendListener guiclass="BackendListenerGui" testclass="BackendListener" testname="Backend Listener" enabled="true">
        <elementProp name="arguments" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" enabled="true">
          <collectionProp name="Arguments.arguments">
            <elementProp name="graphiteMetricsSender" elementType="Argument">
              <stringProp name="Argument.name">graphiteMetricsSender</stringProp>
              <stringProp name="Argument.value">org.apache.jmeter.visualizers.backend.graphite.TextGraphiteMetricsSender</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="graphiteHost" elementType="Argument">
              <stringProp name="Argument.name">graphiteHost</stringProp>
              <stringProp name="Argument.value">10.104.110.163</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="graphitePort" elementType="Argument">
              <stringProp name="Argument.name">graphitePort</stringProp>
              <stringProp name="Argument.value">2003</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="rootMetricsPrefix" elementType="Argument">
              <stringProp name="Argument.name">rootMetricsPrefix</stringProp>
              <stringProp name="Argument.value">jmeter.</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="summaryOnly" elementType="Argument">
              <stringProp name="Argument.name">summaryOnly</stringProp>
              <stringProp name="Argument.value">false</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="samplersList" elementType="Argument">
              <stringProp name="Argument.name">samplersList</stringProp>
              <stringProp name="Argument.value">.*</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="useRegexpForSamplersList" elementType="Argument">
              <stringProp name="Argument.name">useRegexpForSamplersList</stringProp>
              <stringProp name="Argument.value">true</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
            <elementProp name="percentiles" elementType="Argument">
              <stringProp name="Argument.name">percentiles</stringProp>
              <stringProp name="Argument.value">90;95;99</stringProp>
              <stringProp name="Argument.metadata">=</stringProp>
            </elementProp>
          </collectionProp>
        </elementProp>
        <stringProp name="classname">org.apache.jmeter.visualizers.backend.graphite.GraphiteBackendListenerClient</stringProp>
      </BackendListener>
      <hashTree/>
      <ResultCollector guiclass="GraphVisualizer" testclass="ResultCollector" testname="Graph Results" enabled="true">
        <boolProp name="ResultCollector.error_logging">false</boolProp>
        <objProp>
          <name>saveConfig</name>
          <value class="SampleSaveConfiguration">
            <time>true</time>
            <latency>true</latency>
            <timestamp>true</timestamp>
            <success>true</success>
            <label>true</label>
            <code>true</code>
            <message>true</message>
            <threadName>true</threadName>
            <dataType>true</dataType>
            <encoding>false</encoding>
            <assertions>true</assertions>
            <subresults>true</subresults>
            <responseData>false</responseData>
            <samplerData>false</samplerData>
            <xml>false</xml>
            <fieldNames>true</fieldNames>
            <responseHeaders>false</responseHeaders>
            <requestHeaders>false</requestHeaders>
            <responseDataOnError>false</responseDataOnError>
            <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
            <assertionsResultsToSave>0</assertionsResultsToSave>
            <bytes>true</bytes>
            <sentBytes>true</sentBytes>
            <threadCounts>true</threadCounts>
            <idleTime>true</idleTime>
            <connectTime>true</connectTime>
          </value>
        </objProp>
        <stringProp name="filename"></stringProp>
      </ResultCollector>
      <hashTree/>
      <ResultCollector guiclass="ViewResultsFullVisualizer" testclass="ResultCollector" testname="View Results Tree" enabled="true">
        <boolProp name="ResultCollector.error_logging">false</boolProp>
        <objProp>
          <name>saveConfig</name>
          <value class="SampleSaveConfiguration">
            <time>true</time>
            <latency>true</latency>
            <timestamp>true</timestamp>
            <success>true</success>
            <label>true</label>
            <code>true</code>
            <message>true</message>
            <threadName>true</threadName>
            <dataType>true</dataType>
            <encoding>false</encoding>
            <assertions>true</assertions>
            <subresults>true</subresults>
            <responseData>false</responseData>
            <samplerData>false</samplerData>
            <xml>false</xml>
            <fieldNames>true</fieldNames>
            <responseHeaders>false</responseHeaders>
            <requestHeaders>false</requestHeaders>
            <responseDataOnError>false</responseDataOnError>
            <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
            <assertionsResultsToSave>0</assertionsResultsToSave>
            <bytes>true</bytes>
            <sentBytes>true</sentBytes>
            <threadCounts>true</threadCounts>
            <idleTime>true</idleTime>
            <connectTime>true</connectTime>
          </value>
        </objProp>
        <stringProp name="filename"></stringProp>
      </ResultCollector>
      <hashTree/>
      <ResultCollector guiclass="StatGraphVisualizer" testclass="ResultCollector" testname="Aggregate Graph" enabled="true">
        <boolProp name="ResultCollector.error_logging">false</boolProp>
        <objProp>
          <name>saveConfig</name>
          <value class="SampleSaveConfiguration">
            <time>true</time>
            <latency>true</latency>
            <timestamp>true</timestamp>
            <success>true</success>
            <label>true</label>
            <code>true</code>
            <message>true</message>
            <threadName>true</threadName>
            <dataType>true</dataType>
            <encoding>false</encoding>
            <assertions>true</assertions>
            <subresults>true</subresults>
            <responseData>false</responseData>
            <samplerData>false</samplerData>
            <xml>false</xml>
            <fieldNames>true</fieldNames>
            <responseHeaders>false</responseHeaders>
            <requestHeaders>false</requestHeaders>
            <responseDataOnError>false</responseDataOnError>
            <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
            <assertionsResultsToSave>0</assertionsResultsToSave>
            <bytes>true</bytes>
            <sentBytes>true</sentBytes>
            <threadCounts>true</threadCounts>
            <idleTime>true</idleTime>
            <connectTime>true</connectTime>
          </value>
        </objProp>
        <stringProp name="filename"></stringProp>
      </ResultCollector>
      <hashTree/>
    </hashTree>
    <WorkBench guiclass="WorkBenchGui" testclass="WorkBench" testname="WorkBench" enabled="true">
      <boolProp name="WorkBench.save">true</boolProp>
    </WorkBench>
    <hashTree>
      <ProxyControl guiclass="ProxyControlGui" testclass="ProxyControl" testname="HTTP(S) Test Script Recorder" enabled="true">
        <stringProp name="ProxyControlGui.port">443</stringProp>
        <collectionProp name="ProxyControlGui.exclude_list">
          <stringProp name="-2063843150">(?i).*\.(bmp|css|js|gif|ico|jpe?g|png|swf|woff|woff2)</stringProp>
          <stringProp name="464902602">(?i).*\.(bmp|css|js|gif|ico|jpe?g|png|swf|woff|woff2)[\?;].*</stringProp>
        </collectionProp>
        <collectionProp name="ProxyControlGui.include_list"/>
        <boolProp name="ProxyControlGui.capture_http_headers">true</boolProp>
        <intProp name="ProxyControlGui.grouping_mode">4</intProp>
        <boolProp name="ProxyControlGui.add_assertion">false</boolProp>
        <stringProp name="ProxyControlGui.sampler_type_name"></stringProp>
        <boolProp name="ProxyControlGui.sampler_redirect_automatically">false</boolProp>
        <boolProp name="ProxyControlGui.sampler_follow_redirects">true</boolProp>
        <boolProp name="ProxyControlGui.use_keepalive">true</boolProp>
        <boolProp name="ProxyControlGui.sampler_download_images">false</boolProp>
        <boolProp name="ProxyControlGui.regex_match">true</boolProp>
        <stringProp name="ProxyControlGui.content_type_include"></stringProp>
        <stringProp name="ProxyControlGui.content_type_exclude"></stringProp>
        <boolProp name="ProxyControlGui.notify_child_sl_filtered">true</boolProp>
        <stringProp name="ProxyControlGui.proxy_prefix_http_sampler_name"></stringProp>
      </ProxyControl>
      <hashTree>
        <ResultCollector guiclass="ViewResultsFullVisualizer" testclass="ResultCollector" testname="View Results Tree" enabled="true">
          <boolProp name="ResultCollector.error_logging">false</boolProp>
          <objProp>
            <name>saveConfig</name>
            <value class="SampleSaveConfiguration">
              <time>true</time>
              <latency>true</latency>
              <timestamp>true</timestamp>
              <success>true</success>
              <label>true</label>
              <code>true</code>
              <message>true</message>
              <threadName>true</threadName>
              <dataType>true</dataType>
              <encoding>true</encoding>
              <assertions>true</assertions>
              <subresults>true</subresults>
              <responseData>true</responseData>
              <samplerData>true</samplerData>
              <xml>true</xml>
              <fieldNames>false</fieldNames>
              <responseHeaders>true</responseHeaders>
              <requestHeaders>true</requestHeaders>
              <responseDataOnError>true</responseDataOnError>
              <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
              <assertionsResultsToSave>0</assertionsResultsToSave>
              <bytes>true</bytes>
              <url>true</url>
              <fileName>true</fileName>
              <hostname>true</hostname>
              <threadCounts>true</threadCounts>
              <sampleCount>true</sampleCount>
              <idleTime>true</idleTime>
              <connectTime>true</connectTime>
            </value>
          </objProp>
          <stringProp name="filename">recording.xml</stringProp>
        </ResultCollector>
        <hashTree/>
      </hashTree>
    </hashTree>
  </hashTree>
</jmeterTestPlan>
