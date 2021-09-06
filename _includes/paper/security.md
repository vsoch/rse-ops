## Security for RSE-ops vs. DevOps

Security is of utmost importance for HPC, and consequently the
environment is much more restricted for the average user than if the
same user was using the cloud. Specifically, instead of a single user
having root, there are potentially thousands of users sharing the same
systems, and thus the systems are structured to ensure scoped
permissions. The user cannot write to anywhere in the system other than
a home or work-space, and the user largely does not have control over
networking, or further customizing a system provided resource. These
points are related to the permissions section.

Within DevOps, a community has formed around best practices for security
called \"DevSecOps\" [@noauthor_undated-yd]. Although there is more
freedom in the cloud, multi-tenant projects still require that different
teams maintain unique namespaces, and that services are deployed to
avoid any kind of security breach or intellectual property violation.
Thus, DevSecOps (akin to DevOps) aims to automate having security checks
for each step in the life-cycle of a cloud service. DevSecOps also is a
community, and strives to increase general awareness about security best
practices. This is a different approach than traditional security
checks, which might have done an evaluation of a piece of software
before deploying it to production, and likely this is still considered
the best practice for HPC. However, ideally there could be an equivalent
movement to focus and work on security best practices, culture, and
community for RSE-ops.

For both these groups, containers present a unique challenge, as it
seems almost impossible to keep track of every container that a user
might bring to a cluster or cloud environment. At best there is security
scanning in the registry (and the user of the container takes notice)
and the container technology is designed in a way to not allow any
escalation of the user to a root user (e.g., Singularity [@singularity],
or Podman [@podman]), unlike cloud container run-times (e.g., Docker
[@docker]).