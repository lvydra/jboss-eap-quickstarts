<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="generator" content="Asciidoctor 2.0.10">
<meta name="author" content="Pete Muir">
<title>greeter: Demonstrates CDI, JPA, JTA, EJB, and JSF</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:300,300italic,400,400italic,600,600italic%7CNoto+Serif:400,400italic,700,700italic%7CDroid+Sans+Mono:400,700">
</head>
<body class="article">
<div id="header">
<h1>greeter: Demonstrates CDI, JPA, JTA, EJB, and JSF</h1>
<div class="details">
<span id="author" class="author">Pete Muir</span><br>
</div>
</div>
<div id="content">
<div id="preamble">
<div class="sectionbody">
<div class="quoteblock abstract">
<blockquote>
The <code>greeter</code> quickstart demonstrates the use of CDI, JPA, JTA, EJB and JSF in JBoss EAP.
</blockquote>
</div>
</div>
</div>
<div class="sect1">
<h2 id="_what_is_it">What is it?</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The <code>greeter</code> quickstart demonstrates the use of CDI, JPA, JTA, EJB and JSF in Red Hat JBoss Enterprise Application Platform.</p>
</div>
<div class="paragraph">
<p>When you deploy this example, two users are automatically created for you: <code>emuster</code> and <code>jdoe</code>. This data is located in the <code>src/main/resources/import.sql file</code>.</p>
</div>
<div class="paragraph">
<p>To test this example:</p>
</div>
<div class="olist arabic">
<ol class="arabic">
<li>
<p>Enter a name in the <strong>username</strong> field and click on <strong>Greet!</strong>.</p>
</li>
<li>
<p>If you enter a username that is not in the database, you get a message <code>No such user exists!</code>.</p>
</li>
<li>
<p>If you enter a valid username, you get a message <code>Hello,</code> followed by the user&#8217;s first and last name.</p>
</li>
<li>
<p>To create a new user, click the <strong>Add a new user</strong> link. Enter the <strong>username</strong>, <strong>first name</strong>, and <strong>last name</strong>, and then click <strong>Add User</strong>. The user is added and a message displays the new user id number.</p>
</li>
<li>
<p>Click on the <code>Greet a user!</code> link to return to the <code>Greet!</code> page.</p>
</li>
</ol>
</div>
</div>
</div>
<div class="sect1">
<h2 id="considerations_for_use_in_a_production_environment">Considerations for Use in a Production Environment</h2>
<div class="sectionbody">
<div class="dlist">
<dl>
<dt class="hdlist1">H2 Database</dt>
<dd>
<p>This quickstart uses the H2 database included with Red Hat JBoss Enterprise Application Platform 7.4. It is a lightweight, relational example datasource that is used for examples only. It is not robust or scalable, is not supported, and should NOT be used in a production environment.</p>
</dd>
<dt class="hdlist1">Datasource Configuration File</dt>
<dd>
<p>This quickstart uses a <code>*-ds.xml</code> datasource configuration file for convenience and ease of database configuration. These files are deprecated in JBoss EAP and should not be used in a production environment. Instead, you should configure the datasource using the Management CLI or Management Console. Datasource configuration is documented in the <a href="https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/7.4/html-single/configuration_guide/"><em>Configuration Guide</em></a>.</p>
</dd>
</dl>
</div>
</div>
</div>
<div class="sect1">
<h2 id="system_requirements">System Requirements</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The application this project produces is designed to be run on Red Hat JBoss Enterprise Application Platform 7.4 or later.</p>
</div>
<div class="paragraph">
<p>All you need to build this project is Java 8.0 (Java SDK 1.8) or later and Maven 3.3.1 or later. See <a href="https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN_JBOSS_EAP.adoc#configure_maven_to_build_and_deploy_the_quickstarts">Configure Maven to Build and Deploy the Quickstarts</a> to make sure you are configured correctly for testing the quickstarts.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="use_of_jboss_home_name">Use of the EAP_HOME and QUICKSTART_HOME Variables</h2>
<div class="sectionbody">
<div class="paragraph">
<p>In the following instructions, replace <code><em>EAP_HOME</em></code> with the actual path to your JBoss EAP installation. The installation path is described in detail here: <a href="https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_OF_EAP_HOME.adoc#use_of_product_home_and_jboss_home_variables">Use of <em>EAP_HOME</em> and <em>JBOSS_HOME</em> Variables</a>.</p>
</div>
<div class="paragraph">
<p>When you see the replaceable variable <em>QUICKSTART_HOME</em>, replace it with the path to the root directory of all of the quickstarts.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="start_the_eap_standalone_server">Start the JBoss EAP Standalone Server</h2>
<div class="sectionbody">
<div class="olist arabic">
<ol class="arabic">
<li>
<p>Open a terminal and navigate to the root of the JBoss EAP directory.</p>
</li>
<li>
<p>Start the JBoss EAP server with the default profile by typing the following command.</p>
<div class="listingblock">
<div class="content">
<pre class="highlight nowrap"><code>$ <em>EAP_HOME</em>/bin/standalone.sh </code></pre>
</div>
</div>
<div class="admonitionblock note">
<table>
<tr>
<td class="icon">
<div class="title">Note</div>
</td>
<td class="content">
For Windows, use the <code><em>EAP_HOME</em>\bin\standalone.bat</code> script.
</td>
</tr>
</table>
</div>
</li>
</ol>
</div>
</div>
</div>
<div class="sect1">
<h2 id="build_and_deploy_the_quickstart">Build and Deploy the Quickstart</h2>
<div class="sectionbody">
<div class="olist arabic">
<ol class="arabic">
<li>
<p>Make sure you <a href="#start_the_eap_standalone_server">start the JBoss EAP server</a> as described above.</p>
</li>
<li>
<p>Open a terminal and navigate to the root directory of this quickstart.</p>
</li>
<li>
<p>Type the following command to build the artifacts.</p>
<div class="listingblock">
<div class="content">
<pre class="highlight nowrap"><code>$ mvn clean package wildfly:deploy</code></pre>
</div>
</div>
</li>
</ol>
</div>
<div class="paragraph">
<p>This deploys the <code>greeter/target/greeter.war</code> to the running instance of the server.</p>
</div>
<div class="paragraph">
<p>You should see a message in the server log indicating that the archive deployed successfully.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="_access_the_application">Access the Application</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The application will be running at the following URL: <a href="http://localhost:8080/greeter/" class="bare">http://localhost:8080/greeter/</a>.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="undeploy_the_quickstart">Undeploy the Quickstart</h2>
<div class="sectionbody">
<div class="paragraph">
<p>When you are finished testing the quickstart, follow these steps to undeploy the archive.</p>
</div>
<div class="olist arabic">
<ol class="arabic">
<li>
<p>Make sure you <a href="#start_the_eap_standalone_server">start the JBoss EAP server</a> as described above.</p>
</li>
<li>
<p>Open a terminal and navigate to the root directory of this quickstart.</p>
</li>
<li>
<p>Type this command to undeploy the archive:</p>
<div class="listingblock">
<div class="content">
<pre class="highlight nowrap"><code>$ mvn wildfly:undeploy</code></pre>
</div>
</div>
</li>
</ol>
</div>
</div>
</div>
<div class="sect1">
<h2 id="_server_log_expected_warnings_and_errors">Server Log: Expected Warnings and Errors</h2>
<div class="sectionbody">
<div class="paragraph">
<p>You will see the following warnings in the server log. You can ignore these warnings.</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="highlight nowrap"><code>WFLYJCA0091: -ds.xml file deployments are deprecated. Support may be removed in a future version.

HHH000431: Unable to determine H2 database version, certain features may not work</code></pre>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="run_the_quickstart_in_redhat_codeready_studio_or_eclipse">Run the Quickstart in Red Hat CodeReady Studio or Eclipse</h2>
<div class="sectionbody">
<div class="paragraph">
<p>You can also start the server and deploy the quickstarts or run the Arquillian tests in Red Hat CodeReady Studio or from Eclipse using JBoss tools. For general information about how to import a quickstart, add a JBoss EAP server, and build and deploy a quickstart, see <a href="https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_JBDS.adoc#use_red_hat_jboss_developer_studio_or_eclipse_to_run_the_quickstarts">Use Red Hat CodeReady Studio or Eclipse to Run the Quickstarts</a>.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="debug_the_application">Debug the Application</h2>
<div class="sectionbody">
<div class="paragraph">
<p>If you want to debug the source code of any library in the project, run the following command to pull the source into your local repository. The IDE should then detect it.</p>
</div>
<div class="listingblock">
<div class="content">
<pre>$ mvn dependency:sources</pre>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="getting_started_with_openshift">Getting Started with JBoss EAP for OpenShift</h2>
<div class="sectionbody">
<div class="paragraph">
<p>This document contains the basic instructions to build and deploy this quickstart to JBoss EAP for OpenShift or JBoss EAP for OpenShift Online.</p>
</div>
<div class="paragraph">
<p>See <a href="https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/7.4/html-single/getting_started_with_jboss_eap_for_openshift_container_platform/"><em>Getting Started with JBoss EAP for OpenShift Container Platform</em></a> for more detailed information about building and running applications on JBoss EAP for OpenShift.</p>
</div>
<div class="paragraph">
<p>See <a href="https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/7.4/html-single/getting_started_with_jboss_eap_for_openshift_online/"><em>Getting Started with JBoss EAP for OpenShift Online</em></a> for more detailed information about building and running applications on JBoss EAP for OpenShift Online.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="prepare_openshift_for_quickstart_deployment">Prepare OpenShift for Quickstart Deployment</h2>
<div class="sectionbody">
<div class="olist arabic">
<ol class="arabic">
<li>
<p>Log in to your OpenShift instance using the <code>oc login</code> command.</p>
</li>
<li>
<p>Create a new project for the quickstart in OpenShift. You can create a project in OpenShift using the following command.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc new-project greeter-project</pre>
</div>
</div>
<div class="paragraph">
<p>Before you can import and use the OpenShift image for JBoss EAP for OpenShift , you must configure authentication to the Red Hat Container Registry.</p>
</div>
</li>
</ol>
</div>
<div class="paragraph">
<p>Create an authentication token using a registry service account to configure access to the Red Hat Container Registry. You need not use or store your Red&nbsp;Hat account&#8217;s username and password in your OpenShift configuration when you use an authentication token.</p>
</div>
<div class="olist arabic">
<div class="title">Procedure</div>
<ol class="arabic">
<li>
<p>Follow the instructions on Red&nbsp;Hat Customer Portal to create an authentication token using a registry service account.</p>
</li>
<li>
<p>Download the YAML file containing the OpenShift secret for the token.</p>
<div class="paragraph">
<p>You can download the YAML file from the <strong>OpenShift Secret</strong> tab on your token&#8217;s <strong>Token Information</strong> page.</p>
</div>
</li>
<li>
<p>Create the authentication token secret for your OpenShift project using the YAML file that you downloaded:</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">oc create -f <em>1234567_myserviceaccount-secret.yaml</em></pre>
</div>
</div>
</li>
<li>
<p>Configure the secret for your OpenShift project using the following commands, replacing the secret name below with the name of your secret created in the previous step.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">oc secrets link default <em>1234567-myserviceaccount-pull-secret</em> --for=pull
oc secrets link builder <em>1234567-myserviceaccount-pull-secret</em> --for=pull</pre>
</div>
</div>
<div class="ulist">
<div class="title">Additional resources</div>
<ul>
<li>
<p><a href="https://access.redhat.com/RegistryAuthentication#registry-service-accounts-for-shared-environments-4">Create an authentication token using a registry service account</a></p>
</li>
<li>
<p><a href="https://access.redhat.com/documentation/en-us/openshift_container_platform/3.11/html/developer_guide/dev-guide-managing-images#allowing-pods-to-reference-images-from-other-secured-registries">Configuring access to secured registries</a></p>
</li>
<li>
<p><a href="https://access.redhat.com/RegistryAuthentication">Configuring authentication to the Red Hat Container Registry</a></p>
</li>
</ul>
</div>
</li>
</ol>
</div>
</div>
</div>
<div class="sect1">
<h2 id="import_imagestreams_templates">Import the Latest JBoss EAP for OpenShift Imagestreams and Templates</h2>
<div class="sectionbody">
<div class="admonitionblock important">
<table>
<tr>
<td class="icon">
<div class="title">Important</div>
</td>
<td class="content">
<div class="paragraph">
<p>If you are building and deploying this quickstart on JBoss EAP for OpenShift, you must configure authentication to the Red Hat Container Registry before you import the image streams and templates into your namespace. <a href="https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/7.4/html-single/getting_started_with_jboss_eap_for_openshift_container_platform/#container_registry_authentication"><em>Getting Started with JBoss EAP for OpenShift Container Platform</em></a> provides an example of one way to configure authentication to the registry. For additional information, see <a href="https://access.redhat.com/RegistryAuthentication">Red Hat Container Registry Authentication</a> on the Red Hat Customer Portal.</p>
</div>
<div class="paragraph">
<p>Configuration of authentication to the registry is not necessary if you are building and deploying this quickstart on JBoss EAP for OpenShift Online.</p>
</div>
</td>
</tr>
</table>
</div>
<div class="olist arabic">
<div class="title">Procedure</div>
<ol class="arabic">
<li>
<p>Use the following commands to import the latest JDK 8 and JDK 11 image streams and templates for the OpenShift image for JBoss EAP for OpenShift, into your OpenShift project&#8217;s namespace.</p>
<div class="olist loweralpha">
<ol class="loweralpha" type="a">
<li>
<p>Import JDK 8 image streams:</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">oc replace --force -f https://raw.githubusercontent.com/jboss-container-images/jboss-eap-openshift-templates/eap74/eap74-openjdk8-image-stream.json</pre>
</div>
</div>
<div class="paragraph">
<p>This command imports the following imagestreams:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>The JDK 8 builder imagestream: jboss-eap74-openjdk8-openshift</p>
</li>
<li>
<p>The JDK 8 runtime imagestream: jboss-eap74-openjdk8-runtime-openshift</p>
</li>
</ul>
</div>
</li>
<li>
<p>Import JDK 11 image stream:</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">oc replace --force -f https://raw.githubusercontent.com/jboss-container-images/jboss-eap-openshift-templates/eap74/eap74-openjdk11-image-stream.json</pre>
</div>
</div>
<div class="paragraph">
<p>This command imports the following imagestreams:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>The JDK 11 builder imagestream: jboss-eap74-openjdk11-openshift</p>
</li>
<li>
<p>The JDK 11 runtime imagestream: jboss-eap74-openjdk11-runtime-openshift</p>
</li>
</ul>
</div>
</li>
<li>
<p>Import the JDK 8 and JDK 11 templates:</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">for resource in \
  eap74-amq-persistent-s2i.json \
  eap74-amq-s2i.json \
  eap74-basic-s2i.json \
  eap74-https-s2i.json \
  eap74-sso-s2i.json \
  eap74-starter-s2i.json \
  eap74-third-party-db-s2i.json \
  eap74-tx-recovery-s2i.json
do
  oc replace --force -f \
https://raw.githubusercontent.com/jboss-container-images/jboss-eap-openshift-templates/eap74/templates/${resource}
done</pre>
</div>
</div>
</li>
</ol>
</div>
</li>
</ol>
</div>
<div class="admonitionblock note">
<table>
<tr>
<td class="icon">
<div class="title">Note</div>
</td>
<td class="content">
<div class="paragraph">
<p>The JBoss EAP image streams and templates imported using the above command are only available within that OpenShift project.</p>
</div>
<div class="paragraph">
<p>If you have administrative access to the general <code>openshift</code> namespace and want the image streams and templates to be accessible by all projects, add <code>-n openshift</code> to the <code>oc replace</code> line of the command. For example:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="nowrap">...
oc replace -n openshift --force -f \
...</pre>
</div>
</div>
</td>
</tr>
</table>
</div>
</div>
</div>
<div class="sect1">
<h2 id="deploy_eap_s2i">Deploy the JBoss EAP Source-to-Image (S2I) Quickstart to OpenShift</h2>
<div class="sectionbody">
<div class="olist arabic">
<div class="title">Procedure</div>
<ol class="arabic">
<li>
<p>Create a new OpenShift application using the JBoss EAP for OpenShift image and the quickstart&#8217;s source code. Use the following command to use the <code>eap74-basic-s2i</code> template with the JDK 8 images and the <code>greeter</code> source code on GitHub.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc new-app --template=eap74-basic-s2i \
 -p EAP_IMAGE_NAME=jboss-eap74-openjdk8-openshift:latest \
 -p EAP_RUNTIME_IMAGE_NAME=jboss-eap74-openjdk8-runtime-openshift:latest \
 -p IMAGE_STREAM_NAMESPACE="greeter-project" \
 -p SOURCE_REPOSITORY_URL="https://github.com/jboss-developer/jboss-eap-quickstarts" \
 -p SOURCE_REPOSITORY_REF="7.4.x" \
 -p ENABLE_GENERATE_DEFAULT_DATASOURCE="true" \
 -p CONTEXT_DIR="greeter"</pre>
</div>
</div>
<div class="openblock">
<div class="content">
<div class="ulist">
<ul>
<li>
<p><code>--template</code> The template to use.</p>
</li>
<li>
<p><code>-p IMAGE_STREAM_NAMESPACE</code> The latest images streams and templates <a href="#import_imagestreams_templates">were imported into the project&#8217;s namespace</a>, so you must specify the namespace of where to find the image stream. This is usually the OpenShift project&#8217;s name.</p>
</li>
<li>
<p><code>-p SOURCE_REPOSITORY_URL</code> The URL to the repository containing the application source code.</p>
</li>
<li>
<p><code>-p SOURCE_REPOSITORY_REF</code> The Git repository reference to use for the source code. This can be a Git branch or tag reference.</p>
</li>
<li>
<p><code>-p ENABLE_GENERATE_DEFAULT_DATASOURCE</code> Enables the default datasource, which is required by this quickstart.</p>
</li>
<li>
<p><code>-p CONTEXT_DIR</code> The directory within the source repository to build.</p>
</li>
</ul>
</div>
</div>
</div>
<div class="paragraph">
<p>Alternatively, to create the quickstart application using the JDK 11 images enter the following command.</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc new-app --template=eap74-basic-s2i \
 -p EAP_IMAGE_NAME=jboss-eap74-openjdk11-openshift:latest \
 -p EAP_RUNTIME_IMAGE_NAME=jboss-eap74-openjdk11-runtime-openshift:latest \
 -p IMAGE_STREAM_NAMESPACE="greeter-project" \
 -p SOURCE_REPOSITORY_URL="https://github.com/jboss-developer/jboss-eap-quickstarts" \
 -p SOURCE_REPOSITORY_REF="7.4.x" \
 -p ENABLE_GENERATE_DEFAULT_DATASOURCE="true" \
 -p CONTEXT_DIR="greeter"</pre>
</div>
</div>
<div class="openblock">
<div class="content">
<div class="ulist">
<ul>
<li>
<p><code>--template</code> The template to use.</p>
</li>
<li>
<p><code>-p IMAGE_STREAM_NAMESPACE</code> The latest images streams and templates <a href="#import_imagestreams_templates">were imported into the project&#8217;s namespace</a>, so you must specify the namespace of where to find the image stream. This is usually the OpenShift project&#8217;s name.</p>
</li>
<li>
<p><code>-p SOURCE_REPOSITORY_URL</code> The URL to the repository containing the application source code.</p>
</li>
<li>
<p><code>-p SOURCE_REPOSITORY_REF</code> The Git repository reference to use for the source code. This can be a Git branch or tag reference.</p>
</li>
<li>
<p><code>-p ENABLE_GENERATE_DEFAULT_DATASOURCE</code> Enables the default datasource, which is required by this quickstart.</p>
</li>
<li>
<p><code>-p CONTEXT_DIR</code> The directory within the source repository to build.</p>
</li>
</ul>
</div>
</div>
</div>
<div class="admonitionblock note">
<table>
<tr>
<td class="icon">
<div class="title">Note</div>
</td>
<td class="content">
A template can specify default values for many template parameters, and you might have to override some, or all, of the defaults. To see template information, including a list of parameters and any default values, use the command <code>oc describe template <em>TEMPLATE_NAME</em></code>.
</td>
</tr>
</table>
</div>
<div class="admonitionblock tip">
<table>
<tr>
<td class="icon">
<div class="title">Tip</div>
</td>
<td class="content">
It is possible to trim down the JBoss EAP for OpenShift image that will be used to run this quickstart. To do so, please add the <code>-p GALLEON_PROVISION_LAYERS=&lt;galleon layers&gt;</code> argument when creating the new application. Please refer to the JBoss EAP documentation for the list of supported galleon layers.
</td>
</tr>
</table>
</div>
</li>
<li>
<p>Retrieve the name of the build configuration.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc get bc -o name</pre>
</div>
</div>
</li>
<li>
<p>Use the name of the build configurations from the previous step to view the Maven progress of the builds.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc logs -f bc/${APPLICATION_NAME}-build-artifacts

…
Push successful
$ oc logs -f bc/${APPLICATION_NAME}
…
Push successful</pre>
</div>
</div>
<div class="paragraph">
<p>For example, for the previously created application, the following command shows the progress of the Maven builds.</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc logs -f bc/eap74-basic-app-build-artifacts

…
Push successful
$ oc logs -f bc/eap74-basic-app
…
Push successful</pre>
</div>
</div>
</li>
</ol>
</div>
</div>
</div>
<div class="sect1">
<h2 id="post_deployment">OpenShift Post Deployment Tasks</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Depending on your application, you might need to complete some tasks after your OpenShift application has been built and deployed.</p>
</div>
<div class="paragraph">
<p>Examples of post-deployment tasks include the following:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Exposing a service so that the application is viewable from outside of OpenShift.</p>
</li>
<li>
<p>Scaling your application to a specific number of replicas.</p>
</li>
</ul>
</div>
<div class="olist arabic">
<div class="title">Procedure</div>
<ol class="arabic">
<li>
<p>Get the service name of your application using the following command.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc get service</pre>
</div>
</div>
</li>
<li>
<p><strong>Optional</strong>: Expose the main service as a route so you can access your application from outside of OpenShift. For example, for the previously created application, use the following command to expose the required service and port.</p>
<div class="admonitionblock note">
<table>
<tr>
<td class="icon">
<div class="title">Note</div>
</td>
<td class="content">
<div class="paragraph">
<p>If you used a template to create the application, the route might already exist. If it does, continue on to the next step.</p>
</div>
</td>
</tr>
</table>
</div>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc expose service/eap74-basic-app --port=8080</pre>
</div>
</div>
</li>
<li>
<p>Get the URL of the route.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc get route</pre>
</div>
</div>
</li>
<li>
<p>Access the application in your web browser using the URL. The URL is the value of the <code>HOST/PORT</code> field from previous command&#8217;s output.</p>
<div class="admonitionblock note">
<table>
<tr>
<td class="icon">
<div class="title">Note</div>
</td>
<td class="content">
<div class="paragraph">
<p>For example, to interact with this quickstart , the root of its application URLs should be <code>https://<em>HOST_PORT_Value</em>/</code>.</p>
</div>
</td>
</tr>
</table>
</div>
</li>
<li>
<p>Optionally, you can scale up the application instance by running the following command. This command increases the number of replicas to 3.</p>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc scale deploymentconfig <em>DEPLOYMENTCONFIG_NAME</em> --replicas=3</pre>
</div>
</div>
<div class="paragraph">
<p>For example, for this` quickstart, use the following command to scale up the application.</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="nowrap">$ oc scale deploymentconfig/eap74-basic-app --replicas=3</pre>
</div>
</div>
</li>
</ol>
</div>
</div>
</div>
</div>
<div id="footer">
<div id="footer-text">
Last updated 2021-06-23 15:53:25 UTC
</div>
</div>
</body>
</html>