From 1.0.0-rc3 to 1.0.0
=======================
- in `pom.xml` replace `<artifactId>plume-admin</artifactId>` by `<artifactId>plume-admin-ws</artifactId>`
- in all files of the project replace 
`com.coreoz.plume.admin.webservices.security.RestrictToAdmin` by `com.coreoz.plume.admin.jersey.feature.RestrictToAdmin`
- in all files of the project replace 
`com.coreoz.plume.admin.jersey.WebSessionPermission` by `com.coreoz.plume.admin.websession.WebSessionPermission`
- in all files of the project replace 
`com.coreoz.plume.admin.webservices.context.WebSessionAdminFactory` by `com.coreoz.plume.admin.jersey.context.WebSessionAdminFactory`
- in all files of the project replace 
`com.coreoz.plume.admin.webservices.security.AdminSecurityFeature` by `com.coreoz.plume.admin.jersey.feature.AdminSecurityFeature`
- in all files of the project replace `GuiceAdminModule` by `GuiceAdminWsModule`
- in all files of the project replace `GuiceAdminWithDefaultsModule` `GuiceAdminWsWithDefaultsModule`
- if in your Guice configuration you are binding a `WebSessionProvider` class
(e.g. a line with `bind(WebSessionProvider.class).to(WebSessionAdminProvider.class)`), you should add a line
with the same binding for the class `WebSessionClassProvider`,
e.g. `bind(WebSessionClassProvider.class).to(WebSessionAdminProvider.class)`
- if `AuthenticatedUser.of()` is used, it must be replaced by `AuthenticatedUserAdmin.of()`
