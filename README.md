rediscluster-py - a Python interface to a Cluster of Redis key-value store.
===========================================================================

## Installation

    $ sudo pip install rediscluster

or alternatively (you really should be using pip though):

    $ sudo easy_install rediscluster

From source:

    $ sudo python setup.py install
    
## Running Tests

    $ git clone https://github.com/salimane/rediscluster-py.git
    $ cd rediscluster-py
    $ vi tests/config.py
    $ ./run_tests



## Getting Started

    >>> import rediscluster
    >>> cluster = {
    ...          'nodes' : {
    ...                      'node_1' : {'host' : '127.0.0.1', 'port' : 63791},
    ...                      'node_2' : {'host' : '127.0.0.1', 'port' : 63792},
    ...                      'node_5' : {'host' : '127.0.0.1', 'port' : 63795},
    ...                      'node_6' : {'host' : '127.0.0.1', 'port' : 63796}
    ...                    },
    ...          'master_of' : {
    ...                          'node_1' : 'node_6', #node_6 slaveof node_1 in redis6.conf
    ...                          'node_2' : 'node_5'  #node_5 slaveof node_2 in redis5.conf
    ...                        },
    ...          'default_node' : 'node_1'
    ...     }
    >>> r = rediscluster.StrictRedis(cluster=cluster, db=0)
    >>> r.set('foo', 'bar')
    True
    >>> r.get('foo')
    'bar'


## Information

* Code: `git clone git://github.com/salimane/rediscluster-py.git`
* Home: <http://github.com/salimane/rediscluster-py>
* Bugs: <http://github.com/salimane/rediscluster-py/issues>


Author
------

rediscluster-py is developed and maintained by Salimane Adjao Moustapha (me@salimane.com).
It can be found here: http://github.com/salimane/rediscluster-py

