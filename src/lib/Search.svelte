<script>
import {
    HeaderSearch
  } from "carbon-components-svelte";

//search related items
const data = [
    {
      href: "/",
      text: "Kubernetes Service",
      description:
        "Deploy secure, highly available apps in a native Kubernetes experience. IBM Cloud Kubernetes Service creates a cluster of compute hosts and deploys highly available containers.",
    },
    {
      href: "/",
      text: "Red Hat OpenShift on IBM Cloud",
      description:
        "Deploy and secure enterprise workloads on native OpenShift with developer focused tools to run highly available apps. OpenShift clusters build on Kubernetes container orchestration that offers consistency and flexibility in operations.",
    },
    {
      href: "/",
      text: "Container Registry",
      description:
        "Securely store container images and monitor their vulnerabilities in a private registry.",
    },
    {
      href: "/",
      text: "Code Engine",
      description:
        "Run your application, job, or container on a managed serverless platform.",
    },
  ];

  let ref = null;
  let active = false;
  let value = "";
  let selectedResultIndex = 0;
  let events = [];

  $: lowerCaseValue = value.toLowerCase();
  $: results =
    value.length > 0
      ? data.filter((item) => {
          return (
            item.text.toLowerCase().includes(lowerCaseValue) ||
            item.description.includes(lowerCaseValue)
          );
        })
      : [];

  $: console.log("ref", ref);
  $: console.log("active", active);
  $: console.log("value", value);
  $: console.log("selectedResultIndex", selectedResultIndex);
//end search related items
</script>

<HeaderSearch
bind:ref
bind:active
bind:value
bind:selectedResultIndex
placeholder="Search services"
{results}
on:active={() => {
  events = [...events, { type: "active" }];
}}
on:inactive={() => {
  events = [...events, { type: "inactive" }];
}}
on:clear={() => {
  events = [...events, { type: "clear" }];
}}
on:select={(e) => {
  events = [...events, { type: "select", ...e.detail }];
}}
/>