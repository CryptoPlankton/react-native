---
id: version-0.26-segmentedcontrolios
title: segmentedcontrolios
original_id: segmentedcontrolios
---
<a id="content"></a><table width="100%"><tbody><tr><td><h1><a class="anchor" name="segmentedcontrolios"></a>SegmentedControlIOS <a class="hash-link" href="docs/segmentedcontrolios.html#segmentedcontrolios">#</a></h1></td><td style="text-align:right;"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Components/SegmentedControlIOS/SegmentedControlIOS.ios.js">Edit on GitHub</a></td></tr></tbody></table><div><div><p>Use <code>SegmentedControlIOS</code> to render a UISegmentedControl iOS.</p><h4><a class="anchor" name="programmatically-changing-selected-index"></a>Programmatically changing selected index <a class="hash-link" href="docs/segmentedcontrolios.html#programmatically-changing-selected-index">#</a></h4><p>The selected index can be changed on the fly by assigning the
selectIndex prop to a state variable, then changing that variable.
Note that the state variable would need to be updated as the user
selects a value and changes the index, as shown in the example below.</p><div class="prism language-javascript">&lt;SegmentedControlIOS
  values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">]</span><span class="token punctuation">}</span>
  selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>selectedIndex<span class="token punctuation">}</span>
  onChange<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">(</span>event<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>selectedIndex<span class="token punctuation">:</span> event<span class="token punctuation">.</span>nativeEvent<span class="token punctuation">.</span>selectedSegmentIndex<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">}</span>
<span class="token operator">/</span><span class="token operator">&gt;</span></div></div><h3><a class="anchor" name="props"></a>Props <a class="hash-link" href="docs/segmentedcontrolios.html#props">#</a></h3><div class="props"><div class="prop"><h4 class="propTitle"><a class="anchor" name="view"></a><a href="docs/view.html#props">View props...</a> <a class="hash-link" href="docs/segmentedcontrolios.html#view">#</a></h4></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="enabled"></a>enabled <span class="propType">bool</span> <a class="hash-link" href="docs/segmentedcontrolios.html#enabled">#</a></h4><div><p>If false the user won't be able to interact with the control.
Default value is true.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="momentary"></a>momentary <span class="propType">bool</span> <a class="hash-link" href="docs/segmentedcontrolios.html#momentary">#</a></h4><div><p>If true, then selecting a segment won't persist visually.
The <code>onValueChange</code> callback will still work as expected.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="onchange"></a>onChange <span class="propType">function</span> <a class="hash-link" href="docs/segmentedcontrolios.html#onchange">#</a></h4><div><p>Callback that is called when the user taps a segment;
passes the event as an argument</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="onvaluechange"></a>onValueChange <span class="propType">function</span> <a class="hash-link" href="docs/segmentedcontrolios.html#onvaluechange">#</a></h4><div><p>Callback that is called when the user taps a segment;
passes the segment's value as an argument</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="selectedindex"></a>selectedIndex <span class="propType">number</span> <a class="hash-link" href="docs/segmentedcontrolios.html#selectedindex">#</a></h4><div><p>The index in <code>props.values</code> of the segment to be (pre)selected.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="tintcolor"></a>tintColor <span class="propType">string</span> <a class="hash-link" href="docs/segmentedcontrolios.html#tintcolor">#</a></h4><div><p>Accent color of the control.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="values"></a>values <span class="propType"><span>[string]</span></span> <a class="hash-link" href="docs/segmentedcontrolios.html#values">#</a></h4><div><p>The labels for the control's segment buttons, in order.</p></div></div></div></div><div><div><table width="100%"><tbody><tr><td><h3><a class="anchor" name="examples"></a>Examples <a class="hash-link" href="docs/segmentedcontrolios.html#examples">#</a></h3></td><td style="text-align:right;"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Examples/UIExplorer/SegmentedControlIOSExample.js">Edit on GitHub</a></td></tr></tbody></table><div class="prism language-javascript"><span class="token string">'use strict'</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> React <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> ReactNative <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react-native'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> <span class="token punctuation">{</span>
  SegmentedControlIOS<span class="token punctuation">,</span>
  Text<span class="token punctuation">,</span>
  View<span class="token punctuation">,</span>
  StyleSheet
<span class="token punctuation">}</span> <span class="token operator">=</span> ReactNative<span class="token punctuation">;</span>

<span class="token keyword">var</span> BasicSegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;View style<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">{</span>marginBottom<span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">}</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
        &lt;View<span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">,</span> <span class="token string">'Three'</span><span class="token punctuation">,</span> <span class="token string">'Four'</span><span class="token punctuation">,</span> <span class="token string">'Five'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> PreSelectedSegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;View<span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token number">0</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> MomentarySegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;View<span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> momentary<span class="token operator">=</span><span class="token punctuation">{</span><span class="token boolean">true</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> DisabledSegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;View<span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS enabled<span class="token operator">=</span><span class="token punctuation">{</span><span class="token boolean">false</span><span class="token punctuation">}</span> values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> ColorSegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;View style<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">{</span>marginBottom<span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">}</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS tintColor<span class="token operator">=</span><span class="token string">"#ff0000"</span> values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">,</span> <span class="token string">'Three'</span><span class="token punctuation">,</span> <span class="token string">'Four'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token number">0</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
        &lt;View<span class="token operator">&gt;</span>
          &lt;SegmentedControlIOS tintColor<span class="token operator">=</span><span class="token string">"#00ff00"</span> values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">,</span> <span class="token string">'Three'</span><span class="token punctuation">]</span><span class="token punctuation">}</span> selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> EventSegmentedControlExample <span class="token operator">=</span> React<span class="token punctuation">.</span><span class="token function">createClass<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  <span class="token function">getInitialState<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">{</span>
      values<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token string">'One'</span><span class="token punctuation">,</span> <span class="token string">'Two'</span><span class="token punctuation">,</span> <span class="token string">'Three'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>
      value<span class="token punctuation">:</span> <span class="token string">'Not selected'</span><span class="token punctuation">,</span>
      selectedIndex<span class="token punctuation">:</span> undefined
    <span class="token punctuation">}</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;View<span class="token operator">&gt;</span>
        &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span> <span class="token operator">&gt;</span>
          Value<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>value<span class="token punctuation">}</span>
        &lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
        &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span> <span class="token operator">&gt;</span>
          Index<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>selectedIndex<span class="token punctuation">}</span>
        &lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
        &lt;SegmentedControlIOS
          values<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>values<span class="token punctuation">}</span>
          selectedIndex<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>selectedIndex<span class="token punctuation">}</span>
          onChange<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onChange<span class="token punctuation">}</span>
          onValueChange<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onValueChange<span class="token punctuation">}</span> <span class="token operator">/</span><span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token function">_onChange<span class="token punctuation">(</span></span>event<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
      selectedIndex<span class="token punctuation">:</span> event<span class="token punctuation">.</span>nativeEvent<span class="token punctuation">.</span>selectedSegmentIndex<span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token function">_onValueChange<span class="token punctuation">(</span></span>value<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
      value<span class="token punctuation">:</span> value<span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> styles <span class="token operator">=</span> StyleSheet<span class="token punctuation">.</span><span class="token function">create<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  text<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    fontSize<span class="token punctuation">:</span> <span class="token number">14</span><span class="token punctuation">,</span>
    textAlign<span class="token punctuation">:</span> <span class="token string">'center'</span><span class="token punctuation">,</span>
    fontWeight<span class="token punctuation">:</span> <span class="token string">'500'</span><span class="token punctuation">,</span>
    margin<span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

exports<span class="token punctuation">.</span>title <span class="token operator">=</span> <span class="token string">'&lt;SegmentedControlIOS&gt;'</span><span class="token punctuation">;</span>
exports<span class="token punctuation">.</span>displayName <span class="token operator">=</span> <span class="token string">'SegmentedControlExample'</span><span class="token punctuation">;</span>
exports<span class="token punctuation">.</span>description <span class="token operator">=</span> <span class="token string">'Native segmented control'</span><span class="token punctuation">;</span>
exports<span class="token punctuation">.</span>examples <span class="token operator">=</span> <span class="token punctuation">[</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Segmented controls can have values'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;BasicSegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Segmented controls can have a pre-selected value'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;PreSelectedSegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Segmented controls can be momentary'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;MomentarySegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Segmented controls can be disabled'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;DisabledSegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Custom colors can be provided'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;ColorSegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span>
    title<span class="token punctuation">:</span> <span class="token string">'Change events can be detected'</span><span class="token punctuation">,</span>
    <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">:</span> ReactElement <span class="token punctuation">{</span> <span class="token keyword">return</span> &lt;EventSegmentedControlExample <span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span> <span class="token punctuation">}</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">]</span><span class="token punctuation">;</span></div></div></div><div class="docs-prevnext"><a class="docs-next" href="docs/slider.html#content">Next →</a></div>