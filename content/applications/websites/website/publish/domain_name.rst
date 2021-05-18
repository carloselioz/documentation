==================
Custom domain name
==================

By default, your Odoo Online database (and website) have an *.odoo.com* domain name,
for *both* the URL and the emails.

But you can change it to a custom one (e.g. www.yourcompany.com).

Good domain name qualities
==========================
Your website address is as important to your branding as the name of your 
business (or organization). So, it's important to put some thought into changing it to a proper
domain.

Here are some tips to consider when thinking of a domain name:

- Simple and obvious
- Easy to remember (*and* spell)
- The shorter, the better
- Avoid special characters
- Aim for a ".com" and/or your country extension

Read more: `How to Choose a Domain Name for Maximum SEO <https://www.searchenginejournal.com/choose-a-domain-name-maximum-seo/158951/>`__

Buy a domain name
=================
Buy your domain name at a popular registrar, like:

- `GoDaddy <https://www.godaddy.com>`__  
- `Namecheap <https://www.namecheap.com>`__  
- `OVH <https://www.ovh.com>`__ 

.. note:: Steps to buy a domain name are pretty straight forward.
   If you have any issues, check out these easy-to-follow tutorials:

   - `GoDaddy <https://roadtoblogging.com/buy-domain-name-from-godaddy>`__
   - `Namecheap <https://www.loudtips.com/buy-domain-name-hosting-namecheap//>`__

   Feel free to buy an email server to have email addresses using your domain name.
   However, *don't* buy any extra service to create (or host) your website.
   That's Odoo's job!

.. _custom_domain:


Apply domain name to Odoo Database
==================================
First, let's authorize the redirection (yourcompany.com -> yourcompany.odoo.com):

* Open your Odoo.com account from your homepage.

.. image:: domain_name/domain_name01.png
   :align: center
   :alt: opening odoo.com account from homepage

* Go to the *Manage Databases* page.

.. image:: domain_name/domain_name02.png
   :align: center
   :alt: manage databases page

* Click on *Domains* to the right of the database you would like to redirect.

.. image:: domain_name/domain_name03.png
   :align: center
   :alt: clicking domains of the database

* A database domain prompt will appear. Enter your custom domain:
  (e.g. www.yourcompany.com).

.. image:: domain_name/domain_name04.png
   :align: center
   :alt: domain name database prompt

You can now apply the redirection from your domain name's manager account:

* Log in to your account, and search for the DNS Zones management page.

* Create a CNAME record *www.yourdomain.com* pointing to *mywebsite.odoo.com*.
  If you want to use the naked domain (e.g. yourdomain.com), you need to redirect 
  *yourdomain.com* to *www.yourdomain.com*.

.. note:: Here are some specific guidelines to create a CNAME record:

   - `GoDaddy <https://be.godaddy.com/fr/help/add-a-cname-record-19236>`__
   - `Namecheap <https://www.namecheap.com/support/knowledgebase/article.aspx/9646/10/how-can-i-set-up-a-cname-record-for-my-domain>`__
   - `OVH <https://www.ovh.co.uk/g1519.exchange_20132016_how_to_add_a_cname_record>`__

Enable SSL (HTTPS) for Odoo Database
====================================

Until recently, Odoo users needed to use a third-party CDN service provider (such as CloudFlare) to
enable SSL.

However, that is *not* required anymore: Odoo generates the certificate for you automatically, using
integration with `Let's Encrypt Certificate Authority and ACME protocol <https://letsencrypt.org/how-it-works/>`__.
In order to get this, simply add your domain name in your customer portal (a separate certificate is
generated for each domain name specified).

.. warning::
  **Please note that the certificate generation may take up to 24h.**

If you already use CloudFlare (or a similar service), you can keep using it, or simply change to
Odoo. The choice is yours.


Make sure all URLs use custom domain
====================================

To set up the root URL of your website, and of all the links sent in emails, you can ask an
administrator of your database (any user in the *Settings* group) to perform a login from the login
screen. It's as simple as that!

If you want to do it manually, you can go to :menuselection:`Settings --> Technical --> System Parameters` . 
Find the entry called ``web.base.url`` (you can create it, if it does not exist) and enter the full
URL of your website, like ``https://www.myodoowebsite.com``.

.. warning::
  The URL must include the protocol (``https://`` or ``http://``) and must not end with a
  slash (``/``).

If you want to block the root URL update when an administrator logs in, you can add a System
Parameter called  ``web.base.url.freeze`` with its value set to  ``True``.


Website indexed twice by Google
===============================

If you set up a custom domain name (*mydomain.com*) for *mydatabase.odoo.com*,
Google indexes your website under *both* names. This is a minor limitation of the Odoo cloud
platforms.

