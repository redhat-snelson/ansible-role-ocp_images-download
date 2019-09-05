Role Name
=========

Downloads OpenShift Images to the local machine. Another role is used to Transfer OpenShift Images
to a disconnected/ofline Container Registry for use with a Red Hat OpenShift install.

Requirements
------------

Requires Skopeo for downloading Container Images.

Role Variables
--------------

The following variables may need to be set, defaults found in `defaults/main/*.yml`:

The Source Registry credentials and URL variables are as follow:
    src_registry_user: ""
    src_registry_passwd: ""
    src_registry_url: "registry.access.redhat.com/"

The specific container image versions could be set as follow:
    ocp_container_tag_major: "v3.11"
    ocp_container_tag_full: "v3.11.135"
    ocp_container_tag_pod: "v3.11.98"
    ocp_container_tag_deployer: "v3.11.135"
    ocp_container_tag_etcd: "3.2.22"
    s2i_container_tag: "latest"

You should also have three image lists that define the images to download for OpenShift (as YAML)
    docker_image_list_required
    docker_image_list_optional
    docker_image_list_s2i

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: snelson_redhat.ocp_images.download
          src_registry_user: redhataccessuser
          src_registry_passwd: redhataccesspasswd

License
-------

MIT / BSD

Author Information
------------------

This role was written in 2019 by Sean Nelson

